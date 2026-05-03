# What is ASP.NET Core?

## Definition
- **ASP.NET Core** is a **cross-platform, open-source application framework**.
- It is used to build **dynamic web applications quickly**.

## Application types
- ASP.NET Core can build:
  - **server-rendered web applications**
  - **backend server applications**
  - **HTTP APIs** consumable by mobile applications
  - **many other application types**

## Runtime
- ASP.NET Core runs on **.NET 7**.
- **.NET 7** is the latest version of .NET Core.
- It is a **high-performance, cross-platform, open-source runtime**.

## How the framework works
- ASP.NET Core provides:
  - **structure for building applications**
  - **helper functions**
  - a framework that saves you from writing boilerplate code
- The ASP.NET Core framework code calls in to your **handlers**.
- Handlers then call methods in your application’s **business logic**.
- Business logic is the **core of your application**.
- Business logic can interact with services such as **databases** or **remote APIs**.
- Business logic typically does not depend directly on ASP.NET Core.

## Application layers
- A typical ASP.NET Core application consists of several layers:
  - ASP.NET Core framework code handles requests from a client and deals with networking complexity
  - **handlers** (Razor Pages, Web API controllers) are written using framework primitives
  - handlers call into **application domain logic**, typically C# classes and objects without ASP.NET Core-specific dependencies
