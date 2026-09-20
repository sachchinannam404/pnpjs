![SharePoint Patterns and Practices Logo](https://raw.githubusercontent.com/pnp/media/master/pnp-logos-sp/png/1x/SharePoint_PnP_mark_fullcolor.png)

> **Note:** This documentation tree is published from a **personal fork** of [pnp/pnpjs](https://github.com/pnp/pnpjs).
> Issues, questions, and pull requests should normally target the **upstream** repository so the community and npm packages benefit.

PnPjs is a collection of fluent libraries for consuming SharePoint, Graph, and Office 365 REST APIs in a type-safe way. You can use it within SharePoint Framework, Node.js, or any JavaScript project. This is an open-source initiative and we encourage contributions and constructive feedback from the community.

These articles provide general guidance for working with the libraries. If you are migrating from an earlier major version, review the appropriate transition guide:

* [V3 → V4](transition-guide.md)
* [V2 → V3](https://pnp.github.io/pnpjs/v3/transition-guide/)
* [V1 → V2](https://pnp.github.io/pnpjs/v2/transition-guide/)

* **[Getting Started](getting-started.md)**
* [Authentication](concepts/authentication.md)
* [Get Started Contributing](contributing/index.md)

![Fluent API in action](img/PnPjsFluentAPI.gif)

_Animation of the library in use, note intellisense help in building your queries_

## Packages

Patterns and Practices client side libraries (PnPjs) are comprised of the packages listed below. All of the packages are published as a set and depend on their peers within the `@pnp` scope.

The latest published version is [![npm version](https://badge.fury.io/js/%40pnp%2Fcore.svg)](https://badge.fury.io/js/%40pnp%2Fcore).

|     ||  |
| ---| -------------|-------------|
| @pnp/| | |
|| [azidjsclient](./concepts/auth-nodejs)  | Provides an Azure Identity wrapper suitable for use with PnPjs |
|| [core](./packages#core)  | Provides shared functionality across all pnp libraries |
|| [graph](./packages#graph) | Provides a fluent api for working with Microsoft Graph |
|| [logging](./packages#logging) | Light-weight, subscribable logging framework |
|| [msaljsclient](./concepts/authentication)  | Provides an msal wrapper suitable for use with PnPjs |
|| [nodejs](./packages#nodejs) | Provides functionality enabling the @pnp libraries within nodejs |
|| [queryable](./packages#queryable) | Provides shared query functionality and base classes |
|| [sp](./packages#sp) | Provides a fluent api for working with SharePoint REST |
|| [sp-admin](./packages#sp-admin) | Provides a fluent api for working with M365 Tenant admin methods |

## Authentication

We have a section dedicated to helping you [figure out the best way to handle authentication](concepts/authentication.md) in your application.

## Issues, Questions, Ideas

Please [log an issue](https://github.com/pnp/pnpjs/issues) on the **upstream** repository using the issue template as a guide. This lets maintainers track your request and respond. We appreciate constructive feedback, questions, ideas, or bug reports.

## Changelog

Please review the [CHANGELOG](https://github.com/pnp/pnpjs/blob/version-4/CHANGELOG.md) for release details on library changes.

## Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

### "Sharing is Caring"

Please use [http://aka.ms/community/home](http://aka.ms/community/home) for the latest updates around the whole *Microsoft 365 and Power Platform Community (PnP)* initiative.

### Disclaimer

**THIS CODE IS PROVIDED _AS IS_ WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**
