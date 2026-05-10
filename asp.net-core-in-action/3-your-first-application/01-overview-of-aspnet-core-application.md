# Overview of an ASP.NET Core Application

## Request-Response Flow
- Browser makes an HTTP request to the server
- Server receives the request and generates a response
- ASP.NET Core allows **dynamic HTML generation** based on request specifics (e.g., logged-in user)

## Application Architecture Components

### Reverse Proxy
- Common deployment pattern for ASP.NET Core applications
- Sits in front of the ASP.NET Core web server

### ASP.NET Core Web Server (Kestrel)
- Default **cross-platform** HTTP server
- Takes raw incoming network request
- Constructs an `HttpContext` object for the rest of the application

### HttpContext Object
- Used as a **storage box** for a single request
- Contains:
  - Properties of the request
  - Request-specific services
  - Loaded data
  - Errors that occurred
- Passed through the entire application pipeline

### Alternative Servers
- **IIS HTTP Server** — used when running in-process in IIS
- **HTTP.sys** — Windows only, cannot be used with IIS

## Middleware Pipeline
- Series of components that process incoming requests
- Executes in **sequence**
- Performs common operations:
  - Logging
  - Handling exceptions
  - Serving static files
  - User identification
  
## Endpoint Middleware
- Located at the **end** of the middleware pipeline
- Responsible for calling code that generates the final response
- Types of endpoints:
  - Model-View-Controller (MVC)
  - Razor Pages
  - Minimal API endpoints