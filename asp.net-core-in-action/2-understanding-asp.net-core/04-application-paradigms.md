# Understanding the Many Paradigms of ASP.NET Core

## Core paradigms overview
- ASP.NET Core provides a **generalized web framework** for building a wide variety of applications.
- Paradigms support different styles of web applications and APIs.

## Paradigm types

### Minimal APIs
- **Simple HTTP APIs** consumed by mobile applications or browser-based single-page applications (SPAs).

### Web APIs
- **Alternative approach** for building HTTP APIs.
- Adds **more structure and features** than minimal APIs.

### gRPC APIs
- Used for building **efficient binary APIs**.
- For **server-to-server communication** using the gRPC protocol.

### Razor Pages
- Used for building **page-based server-rendered applications**.

### MVC controllers
- **Similar to Razor Pages**.
- Used for **server-based applications**.
- Without the **page-based paradigm**.

### Blazor WebAssembly
- **Browser-based SPA framework**.
- Uses the **WebAssembly standard**.
- Similar to JavaScript frameworks such as **Angular, React, and Vue**.

### Blazor Server
- Used for building **stateful applications**.
- **Rendered on the server**.
- Send **UI events and page updates over WebSockets**.
- Provides the feel of a **client-side SPA**.
- Ease of development of a **server-rendered application**.

## Shared foundation
- All paradigms use the **core functionality of ASP.NET Core**.
- Layer **additional functionality on top**.
- Each paradigm is **suited to a different style** of web application or API.

## Server-rendered web applications
- **Bread and butter of ASP.NET development**.
- Both previous ASP.NET and ASP.NET Core support this paradigm.
- **Razor Pages** and **MVC controller** paradigms provide two slightly different styles.
- Share **many of the same concepts**.
- Useful for building **rich, dynamic websites**:
  - **E-commerce sites**
  - **Content management systems (CMSes)**
  - **Large n-tier applications**

## Examples of server-rendered applications
- **Orchard Core**: open-source CMS built with ASP.NET Core.
- **cloudscribe CMS**: project built with ASP.NET Core.

## REST and HTTP APIs
- ASP.NET Core is **ideally suited** to building a **REST** or **HTTP API** server.
- Used for building backends for:
  - **Mobile apps**
  - **JavaScript SPAs** using Angular, React, Vue, or other frameworks
- Easy to create an ASP.NET Core application as the **server-side API**.
- Use **minimal API** and **web API** paradigms.

## REST definition
- **REST** stands for **representational state transfer**.
- RESTful applications typically use:
  - **Lightweight and stateless** HTTP calls
  - **Read, post (create/update), and delete** data

## Beyond RESTful services
- ASP.NET Core is not restricted to creating RESTful services.
- Easy to create a **web service** or **remote procedure call (RPC)-style service**.
- Example: using **gRPC**.
- Your application might expose only a **single endpoint**.
- ASP.NET Core is perfectly designed for **building simple services**.
- Thanks to:
  - **Cross-platform support**
  - **Lightweight design**

## gRPC definition
- **gRPC** is a **modern open-source, high-performance RPC framework**.
- More information at https://grpc.io.

## Application versatility
- ASP.NET Core can act as the **server-side application** for a variety of clients.
- Can **serve HTML pages** for traditional web applications.
- Can act as a **REST API** for client-side SPA applications.
- Can act as an **ad hoc RPC service** for client applications.

## Blazor frameworks

### Blazor WebAssembly (WASM)
- Apps **run directly in your browser**.
- Same way as **traditional JavaScript SPA frameworks** like Angular and React.
- **.NET code** is compiled to **WebAssembly** or executes on a **.NET runtime** compiled for WASM.
- Browser **downloads and runs it** as it would a JavaScript app.
- Build **highly interactive client-side applications**.
- Use **C#** and all **.NET APIs and libraries** you already know.

### Blazor Server
- Applications run on the **server**.
- Each **mouse click or keyboard event** is sent to the server via **WebSockets**.
- Server calculates **changes** that should be made to the **UI**.
- Server sends **required changes back** to the client.
- Client **updates the page in the browser**.
- Results in a **\"stateful\"** application that runs **server-side**.
- Can build **highly interactive SPAs**.
- Main downside: requires a **constant internet connection**.

## Focus of this book
- This book focuses on:
  - **Traditional page-based, server-side-rendered web applications**
  - **RESTful web APIs**
  - **Background worker services** (chapter 34)
- For more information on **Blazor**: see Blazor in Action, by Chris Sainty (Manning, 2022).

## Choosing a paradigm
- With multiple paradigm options, you can **use ASP.NET Core** to build a wide variety of applications.
- Still worth considering whether **ASP.NET Core is right** for your specific application.
- Decision affected by:
  - **Experience with .NET**
  - **Type of application** you want to build
