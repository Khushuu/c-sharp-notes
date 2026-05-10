# Creating Your First ASP.NET Core Application

## Application Types Available

| Type | Description |
|------|-------------|
| **Minimal API** | HTTP API returning JSON, consumed by SPAs and mobile apps |
| **Razor Pages** | Server-side HTML generation for direct browser viewing |
| **MVC** | Similar to Razor Pages, uses traditional MVC controllers |
| **Web API** | Like minimal APIs with additional functionality, some performance tradeoff |

## Four Steps to Get an Application Running

1. **Generate** — Create base application from a template
2. **Restore** — Restore packages and dependencies using NuGet
3. **Build** — Compile the application and generate artifacts
4. **Run** — Execute the compiled application

## Creating with Visual Studio 2022

- Choose **Create a New Project**
- Select **ASP.NET Core Empty** (C# language template)
- Enter project name, location, and solution name
- Configure:
  - Select **.NET 7.0**
  - Check **Configure for HTTPS**
  - Uncheck **Enable Docker**
  - Uncheck **Do not use top-level statements**

## Creating with .NET CLI

```bash
dotnet new sln -n WebApplication1     # Creates solution file
dotnet new web -o WebApplication1     # Creates empty ASP.NET Core project
dotnet sln add WebApplication1        # Adds project to solution

Key Definitions

Template — Provides basic code required to build an application; starting point for your apps
Project — A unit of deployment, compiled into a .dll or executable
Solution — Contains multiple projects that can be built and developed together
Building the Application

Visual Studio: Build > Build Solution or Ctrl-Shift-B
CLI: dotnet build
Both tools automatically restore packages when creating projects
Both tools automatically build when running if changes are detected