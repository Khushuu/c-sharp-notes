
---

## 06-program-cs-file.md

```markdown
# Program.cs File

## Overview

- Defines the **entry point** for ASP.NET Core applications
- All ASP.NET Core apps start as .NET Console applications
- Uses **top-level statements** (C# 9+)

## Top-Level Statements

### Before C# 9 (Explicit Main)
```csharp
using System;
namespace MyApp
{
    public class Program
    {
        public static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}

## With Top-Level Statements (C# 9+)


Console.WriteLine("Hello World!");
Compiler generates the Main method automatically
args variable available as string[] even without explicit declaration
Use --use-program-main CLI option for explicit Main function


## Default Program.cs Structure


WebApplicationBuilder builder = WebApplication.CreateBuilder(args);
WebApplication app = builder.Build();
app.MapGet("/", () => "Hello World!");
app.Run();

## WebApplicationBuilder
Created by WebApplication.CreateBuilder() and configures:

Feature	                Description
Configuration	        Loads values from JSON files and environment variables
Logging	                Extensible logging system for observability and debugging
Services	            Registers classes for dependency injection
Hosting	                Uses Kestrel web server by default##


## WebApplication
Created by calling Build() on the builder. Defines:

Middleware — Components executing in sequence for HTTP requests
Endpoints — Define how responses are generated for specific URLs

## MapGet Function

app.MapGet("/", () => "Hello World!");
First argument: URL path to respond to
Second argument: delegate that returns the response
Other Map* functions exist for different HTTP verbs (MapPost, etc.)

## HTTP Verbs

Verb	    Purpose
GET	        Fetches a resource (default when browsing)
POST	    Sends data to the server (e.g., form submission)

## Key Point

After Build() is called, no more services can be registered
HTTP server starts listening only after Run() is called