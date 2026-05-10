
---

## 07-adding-functionality.md

```markdown
# Adding Functionality to Your Application

## Six Steps of Application Setup

1. Create a `WebApplicationBuilder` instance
2. Register services and configuration with the builder
3. Call `Build()` to create `WebApplication` instance
4. Add middleware to create a pipeline
5. Map endpoints in your application
6. Call `Run()` to start the server

## Extended Example

```csharp
using Microsoft.AspNetCore.HttpLogging;

WebApplicationBuilder builder = WebApplication.CreateBuilder(args);

builder.Services.AddHttpLogging(opts =>
    opts.LoggingFields = HttpLoggingFields.RequestProperties);

builder.Logging.AddFilter(
    "Microsoft.AspNetCore.HttpLogging", LogLevel.Information);

WebApplication app = builder.Build();

if (app.Environment.IsDevelopment())
{
    app.UseHttpLogging();
}

app.MapGet("/", () => "Hello World!");
app.MapGet("/person", () => new Person("Andrew", "Lock"));

app.Run();

public record Person(string FirstName, string LastName);

## Services and Dependency Injection

## Key Concepts
Service — Any class providing functionality to an application
Single-Responsibility Principle (SRP) — Each class responsible for only one piece of functionality
Dependency Injection (DI) — Declare dependencies and let another class fill them
IoC Container — Registers and creates service instances

## Registering Services

builder.Services.AddHttpLogging(opts =>
    opts.LoggingFields = HttpLoggingFields.RequestProperties);

Use Services property on WebApplicationBuilder
Extension methods encapsulate setup code (common pattern)

## Middleware
Characteristics
Small components executing in sequence
Order of Use* calls matters
Can only access objects created by previous middleware

## Adding Middleware

if (app.Environment.IsDevelopment())
{
    app.UseHttpLogging();
}

Auto-Added  Middleware by WebApplication
Middleware	            Position	                Purpose
Routing Middleware	    Start of pipeline	        Determines which endpoint to invoke
Endpoint Middleware	    End of pipeline	            Executes the selected endpoint
Error-handling	        Auto-added in development	Handles exceptions


## IWebHostEnvironment
Accessed via app.Environment, exposes:

Property	                Description
ContentRootPath	            Working directory for the app
WebRootPath	                Location of wwwroot folder for static files
EnvironmentName	            Current environment (Development/Production)

Set externally via environment variable at app startup

## Endpoints

Minimal API Endpoints

app.MapGet("/", () => "Hello World!");
app.MapGet("/person", () => new Person("Andrew", "Lock"));
Response Types

Return Type	    Behavior
string	        Returned as plain text
C# object	    Serialized to JSON automatically

Path Definition

Path — Remainder of URL after domain
Example: www.example.org/account/manage → path is /account/manage

## Request Flow Summary

Request arrives at ASP.NET Core web server
Routing middleware selects appropriate endpoint
Request passes through remaining middleware
Endpoint middleware executes the lambda/handler
Response passes back through middleware
Response sent to browser