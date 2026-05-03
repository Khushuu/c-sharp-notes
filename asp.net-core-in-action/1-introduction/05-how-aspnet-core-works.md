# How Does ASP.NET Core Work?

## Section goal
- Explain how an ASP.NET Core application processes requests.
- Cover the flow from a browser URL request to page display.
- Compare generic HTTP requests with ASP.NET Core request handling.

## How does an HTTP web request work?

- ASP.NET Core is a framework for building web applications that serve data from a server.
- Common scenario: a web app viewable in a browser.
- Request flow begins when a user navigates to a website or types a URL.
- A URL contains:
  - a **hostname**
  - a **path** to a resource
- Browser sends a request to the hosting server using **HTTP**.

### Hostname definition
- **Hostname** uniquely identifies a website location on the internet.
- It maps via **DNS** to an IP address.
- Examples: **microsoft.com**, **www.google.co.uk**, **facebook.com**.

### HTTP primer
- **HTTP** is the application-level protocol powering the web.
- It is a **stateless request-response protocol**.
- Client sends a request, server sends a response.
- Every request contains:
  - a **verb** (GET, POST, etc.)
  - a **path** to a resource
- Requests typically include **headers** and sometimes a **body**.
- Responses contain a **status code** and optionally **headers** and a **body**.

- The request travels through the internet to the server for the hostname.
- It may pass through multiple routers before reaching the server.
- Only the correct server processes the request.
- Server processes the request and generates an **HTTP response**.
- Response types can include:
  - **web page HTML**
  - **images**
  - **JavaScript files**
  - **acknowledgment messages**
  - practically any other file type

- Example: the home page response contains HTML.
- The server sends the response back across the internet to the browser.
- The browser starts displaying content as it arrives.
- The HTML may reference additional files.
- Browser requests referenced files using the same HTTP process.
- Additional resources include **images**, **CSS**, and **JavaScript**.
- Modern web pages may require hundreds of requests.

## How does ASP.NET Core process a request?

- ASP.NET Core apps still use standard **HTTP**.
- ASP.NET Core handles server-side processing, including:
  - **request validation**
  - **authentication and login handling**
  - **HTML generation**
- Request enters the ASP.NET Core application via the network.
- Every ASP.NET Core app includes a built-in web server, usually **Kestrel**.
- Kestrel receives raw requests and builds an **HttpContext** object.
- The application uses HttpContext to generate a response.
- Possible responses include:
  - **HTML pages**
  - **access denied messages**
  - **emails or other outputs**
- After processing, the app returns the response to the web server.
- The web server converts it to raw HTTP.
- The response is sent back to the browser.

- To the user, the flow appears unchanged:
  - **HTTP request sent**
  - **HTTP response received**
- The differences occur on the server side within the application.

## What this means
- ASP.NET Core combines request handling, middleware, and application logic.
- Responses are built dynamically based on incoming requests.
- The book will cover each component of the ASP.NET Core pipeline in detail.
- Response generation happens quickly, often in a fraction of a second.
