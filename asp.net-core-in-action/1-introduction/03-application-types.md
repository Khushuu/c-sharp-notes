# What Types of Applications Can You Build?

## Supported application paradigms
- ASP.NET Core provides a generalized web framework for a wide variety of applications.
- Supported paradigms include:
  - **Minimal APIs** — Simple HTTP APIs consumable by mobile applications or browser-based single-page applications.
  - **Web APIs** — More structured HTTP APIs with additional features than minimal APIs.
  - **gRPC APIs** — Efficient binary APIs for server-to-server communication using the gRPC protocol.
  - **Razor Pages** — Page-based server-rendered applications.
  - **MVC controllers** — Model-View-Controller applications without the page-based paradigm.
  - **Blazor WebAssembly** — Browser-based SPA framework using WebAssembly.
  - **Blazor Server** — Stateful server-rendered applications with UI updates over WebSockets.

## Common foundation
- All paradigms share the same ASP.NET Core building blocks.
- Includes libraries such as **configuration** and **logging**.
- Extra functionality is added on top of shared foundations.

## Choosing the right paradigm
- Select based on:
  - **API requirements**
  - **existing applications** you need to integrate with
  - your customers’ **browsers** and operating environment
  - **scalability** and **uptime requirements**
- ASP.NET Core can combine multiple paradigms in a single application.
