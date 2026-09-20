# Transition Guide V3 → V4

For migrating from an earlier version of PnPjs, see:

- [V2 → V3 Transition Guide](https://pnp.github.io/pnpjs/v3/transition-guide/)
- [V1 → V2 Transition Guide](https://pnp.github.io/pnpjs/v2/transition-guide/)

It is our hope that the transition from version 3.x to 4.x will be as painless as possible; the changes are not as extensive as with version 3. Below are highlights of the most disruptive changes. For a full list of what was added, updated, and removed, see the [CHANGELOG](https://github.com/pnp/pnpjs/blob/version-4/CHANGELOG.md).

## SharePoint Taxonomy has moved to @pnp/graph from @pnp/sp

To better support Taxonomy authentication and control, Taxonomy was moved from the `@pnp/sp` module to the `@pnp/graph` module. The previous approach relied on v2.x endpoints inside the SharePoint bundle, which was not ideal long term. Update taxonomy implementations to use the Graph endpoints.

## Add/Update methods no longer returning data and a queryable instance

The primary breaking change is with add and update method return values. Calls return what the endpoint returns instead of an object with a `data` property and a queryable "item" property. Anywhere you referenced `data` on the return object, remove that indirection. Many Graph endpoints already return the added or updated object, so the impact is often only the property path.

SharePoint returns the object for many add operations, but many update operations return **204**, which maps to `void`. In that case, make a second call if you need the updated entity:

```TypeScript
// Version 3
const update = await sp.web.lists.getByTitle("My List").items.getById(1).update({ Title: "My New Title" });
const newTitle = update.data.Title;

// Version 4
await sp.web.lists.getByTitle("My List").items.getById(1).update({ Title: "My New Title" });
const updatedItem = await sp.web.lists.getByTitle("My List").items.getById(1)();
```

When adding items in Graph and SharePoint, the call often returns the created object. Read the new id directly:

```TypeScript
// Version 3
const newItem = await sp.web.lists.getByTitle("My List").items.add({ Title: "My New Title" });
const newItemId = newItem.data.Id;

// Version 4
const newItem = await sp.web.lists.getByTitle("My List").items.add({ Title: "My New Title" });
const newItemId = newItem.Id;
```

## Async Iterator Pattern

Prefer an async iterator pattern when reading more than 5000 items from a list.

The `/items/get-all` endpoint was removed. The `@pnp/sp` `IItems` / `_Items` collections and `@pnp/graph` collection types support the async iterator pattern.

See [Get Paged Items](./sp/items.md#get-paged-items) and [Async Paging](./concepts/async-paging.md).
