# When to Choose ASP.NET Core

## Considerations for platform choice
- When deciding whether to use **ASP.NET Core** and **.NET 7**, consider multiple factors.
- Not all factors are **technical**.
- One important factor is **level of support** you can expect from creators.

## Microsoft support
- For some organizations, **limited support** is an obstacle to adopting open-source software.
- **Microsoft has pledged** to provide full support for **Long Term Support (LTS)** versions.
- **LTS versions** supported for **at least three years** from release.
- Development takes place in the **open** on GitHub.
- Can get answers from **general community** and **Microsoft directly**.

## Two primary dimensions
- Whether you are **already a .NET developer**.
- Whether you are **creating a new application** or converting an existing one.

## If you're new to .NET development

### Advantages
- **Great time to join** as a new developer.
- Many **growing pains** of a new framework have been worked out.
- Resulted in a **stable, high-performance, cross-platform application framework**.

### Primary language: C#
- **C#** is the primary language of .NET development and ASP.NET Core.
- Has a **huge following** for good reason.
- **Object-oriented C-based language**.
- Provides **familiarity** to those used to C, Java, and many other languages.
- Many **powerful features**:
  - **Language Integrated Query (LINQ)**
  - **Closures**
  - **Asynchronous programming constructs**
- **Designed in the open** on GitHub.
- **C# compiler** code-named **Roslyn** (https://github.com/dotnet/roslyn).

### Cross-platform development
- Major advantage over **.NET Framework**.
- With **.NET 7**, you can **build and run the same application** on **Mac, Windows, and Linux**.
- Can **deploy to the cloud** using **tiny container deployments**.

### Containers and deployment
- **Containers** are far more **lightweight** than virtual machines.
- Don't have the **overhead of virtual machines**.
- Built in a **series of layers**.
- Don't require you to **boot a new operating system**.
- **Quick to start** and great for quick provisioning.
- **(Docker in particular)** are becoming the go-to platform.
- **Containers were never attractive** for previous ASP.NET applications.
- With **ASP.NET Core, .NET 7, and Docker for Windows**: all that is changing.
- **Lightweight ASP.NET Core application** running on **cross-platform .NET 7** is perfect for **thin container deployments**.

### Compile once, run anywhere
- One of the selling points of **.NET**.
- **Write and compile only once**.
- Applications compiled to **Intermediate Language (IL) code**.
- IL is a **platform-independent format**.
- If a target system has the **.NET 7 runtime** installed, you can run **compiled IL from any platform**.
- Develop on a **Mac or Windows machine**.
- Deploy **exactly the same files** to your **production Linux machines**.
- **Compile-once, run-anywhere promise** has finally been realized.

### Self-contained deployments
- Go one step further: **package the .NET runtime** with your app.
- Called a **self-contained deployment (SCD)**.
- Deploy **cross-platform** without .NET on the target machine.
- Generated deployment files are **customized for the target machine**.
- No longer **deploying the same files everywhere** in this case.

### Design patterns
- **Many web frameworks** use **similar well-established design patterns**.
- ASP.NET Core is no different.
- **Ruby on Rails** uses the **MVC pattern**.
- **Node.js** processes requests using **small discrete modules** (pipeline).
- **Dependency injection** is available in **wide variety of frameworks**.
- If techniques are **familiar**, transfer to ASP.NET Core is easy.
- If techniques are **new**, you can use **industry best practices**.

### Rich feature set
- ASP.NET Core provides a **rich set of features**.
- Doesn't **overwhelm you with concepts** like legacy ASP.NET framework did.

## If you're a .NET Framework developer creating a new application

### Maturity status
- ASP.NET Core and .NET are now **mature, stable platforms**.
- **Absolutely time** to consider using **.NET 7** for your new apps.

### Cross-platform benefits
- If you aren't using **Windows-specific constructs** (Registry, etc.).
- Ability to **build and deploy cross-platform** opens possibilities:
  - **Cheaper Linux hosting** in the cloud
  - **Develop natively in macOS** without need for virtual machine

### Windows-specific features
- .NET Core and .NET 7 are **inherently cross-platform**.
- You can still use **platform-specific features** if needed.
- **Windows-specific features** such as Registry and Directory Services.
- Can be enabled with a **Compatibility Pack**.
- Makes these APIs available in **.NET 5+**.
- Only available when running **.NET 5+ in Windows**.
- Not available on **Linux or macOS**.
- Need to take care that such applications run only in **Windows environment**.
- Or account for **potential missing APIs**.

### Hosting model changes
- Previous ASP.NET framework used a **complex hosting model**.
- Relied on **Windows IIS** to provide web-server hosting.
- In a **cross-platform environment**, this symbiotic relationship isn't possible.
- Alternative hosting model has been adopted.
- Separates **web applications from underlying host**.


### Kestrel HTTP server
- **Fast, cross-platform HTTP server**.
- ASP.NET Core can run on Kestrel.

### Self-hosting model
- Instead of previous design, where **IIS calls into specific points** of your application.
- **ASP.NET Core applications are console applications**.
- Self-host a **web server** and **handle requests directly**.
- Hosting model is **conceptually much simpler**.
- Allows you to **test and debug** applications from the command line.
- Doesn't necessarily **remove the need to run IIS** in production.

### Reverse proxies
- ASP.NET Core applications can be **exposed directly to the internet**.
- **Kestrel receives requests directly** from the network.
- **More common**: use a reverse proxy between raw network and application.
- In Windows: reverse-proxy server typically is **IIS**.
- In Linux or macOS: might be **NGINX, HAProxy, or Apache**.
- **YARP** (Yet Another Reverse Proxy): ASP.NET Core-based reverse proxy library.

### Reverse proxy benefits
- **Receiving requests** and **forwarding them** to appropriate web server.
- Reverse proxy is **exposed directly to the internet**.
- Underlying web server exposed only to the **proxy**.
- Several benefits, primarily:
  - **Security**
  - **Performance** for web servers
- **Decoupling** of application from underlying operating system.
- **Same ASP.NET Core web server (Kestrel)** can be **cross-platform**.
- Can use behind **variety of proxies** without constraints.
- Alternatively, write a **new ASP.NET Core web server**.
- Use in place of **Kestrel** without changing anything else about application.
- Reverse proxy can be **hardened against potential threats**.
- Often responsible for **restarting processes** that have crashed.
- Kestrel can remain a **simple HTTP server**.
- When used behind reverse proxy, doesn't worry about **extra features**.
- **Simple separation of concerns**:
  - **Kestrel** concerned with generating **HTTP responses**
  - **Reverse proxy** concerned with **handling connection to internet**

### Default Windows deployment
- By default, when running in Windows, **ASP.NET Core runs inside IIS**.
- Can provide **better performance** than reverse-proxy version.
- Primarily a **deployment detail**.
- Doesn't change the way you **build ASP.NET Core applications**.

### Performance improvements
- **Performance was a sore point** for previous ASP.NET applications.
- Possible to build **high-performing applications** (Stack Overflow example).
- **Web framework itself** wasn't designed with **performance as a priority**.
- Could end up being an **obstacle**.

### Kestrel performance
- To make the product **competitive cross-platform**.
- ASP.NET team focused on making **Kestrel as fast as possible**.
- **TechEmpower benchmarks** run on wide range of web frameworks.
- In **round 20** of plain-text benchmarks.
- **ASP.NET Core with Kestrel** was among the **10 fastest of more than 400 frameworks** tested.

### Open-source contributions
- Many **performance improvements** to Kestrel came from **contributors** on GitHub.
- Not only from **ASP.NET team members**.
- Developing in the **open** means fixes and features reach production **faster**.
- Previous ASP.NET version was **dependent on .NET Framework and Windows**.
- Had **long release cycles**.

### Release cadence
- **.NET 5+** and hence **ASP.NET Core** are designed to be released in **small increments**.
- **Major versions** released on **predictable cadence**.
- **New version every year**.
- **New LTS version released every two years**.
- **Bug fixes and minor updates** can be released as needed.
- **Additional functionality** provided in **NuGet packages**.
- Independent of underlying **.NET 5+** platform.

### Modularity
- ASP.NET Core is **highly modular**.
- As little **coupling to other features** as possible.
- Lends itself to a **pay-for-play approach** to dependencies.
- Start with a **bare-bones application**.
- Add only the **libraries you require**.
- Opposite of **kitchen-sink approach** of previous ASP.NET applications.
- Even **MVC is an optional package**.

### ASP.NET Core features
- **Middleware pipeline** for defining application behavior.
- **Built-in support** for dependency injection.
- **Combined UI (MVC)** and **API (web API)** infrastructure.
- **Highly extensible configuration system**.
- **Standardized, extensible logging system**.
- Uses **asynchronous programming by default**.
- Built-in **scalability on cloud platforms**.

### Feature setup
- Previous ASP.NET version required **fair amount of additional work** to set up these features.
- With **ASP.NET Core**: all there, ready and waiting to be connected.

### Microsoft support
- **Microsoft fully supports** ASP.NET Core.
- If you want to **build a new system**, there's **no significant reason not to use it**.
- **Largest obstacle**: wanting to use **programming models no longer supported**.
  - **Web Forms**
  - **WCF Server**

## If you're converting an existing ASP.NET application to ASP.NET Core

### Conversion considerations
- Existing applications **presumably provide value**.
- Should have a **tangible benefit** to converting.
- May amount to a **significant rewrite**.
- Advantages are **much the same** as for new applications:
  - **Cross-platform deployment**
  - **Modular features**
  - **Focus on performance**
- Whether benefits are **sufficient depends** on application characteristics.

### Difficult conversion scenarios
- Your application uses **ASP.NET Web Forms**.
- Your application is built with **WCF**.
- Your application is **large**, with **many advanced MVC features**.

### ASP.NET Web Forms conversion
- Attempting to **convert directly** to ASP.NET Core is **not advisable**.
- **Web Forms** is **inextricably tied** to System.Web.dll and IIS.
- Will **likely never be available** in ASP.NET Core.
- Converting effectively involves **rewriting from scratch**.
- Not only **shifting frameworks**, but potentially **shifting design paradigms**.

### Web Forms alternatives
- **Blazor server** provides a **stateful, component-based application**.
- Similar to the **Web Forms application model**.
- May be able to **gradually migrate** page by page.
- To an **ASP.NET Core Blazor server application**.
- Alternatively: slowly introduce **web API concepts**.
- Reduce reliance on **legacy Web Forms constructs** (ViewState).
- Goal of ultimately moving to **ASP.NET Core web API application**.

### Windows Communication Foundation (WCF)
- **Only partially supported** in ASP.NET Core.
- Possible to build **client-side WCF services**.
- Using libraries provided by ASP.NET Core (https://github.com/dotnet/wcf).
- Possible to build **server-side WCF services**.
- Using **Microsoft-supported community-driven project CoreWCF**.
- Libraries don't support **all APIs** available in .NET Framework WCF.
- Don't support:
  - **Distributed transactions**
  - Some **message security formats**
- If you **absolutely need those APIs**, may be best to **avoid ASP.NET Core** for now.

### gRPC as WCF alternative
- If you like **WCF's contract-based RPC-style programming**.
- But don't have **hard requirement for WCF itself**.
- Consider using **gRPC instead**.
- **Modern RPC framework** with **many similar concepts** to WCF.
- **Supported by ASP.NET Core** out of the box.

### Complex application conversion
- If existing application is **complex**.
- Makes **extensive use** of previous MVC or web API **extensibility points**.
- Makes extensive use of **message handlers**.
- Porting may be **more difficult**.
- ASP.NET Core is built with **many similar features** to previous ASP.NET MVC.
- **Underlying architecture is different**.
- Several previous features don't have **direct replacements**.
- Will require **rethinking**.

### Application size impact
- **Larger the application**, the greater the **difficulty** converting.
- **Microsoft itself suggests** that porting from **ASP.NET MVC to ASP.NET Core**.
- Is at least as **big a rewrite** as porting from **ASP.NET Web Forms to ASP.NET MVC**.

### When not to convert
- If application is **rarely used**.
- Isn't part of your **core business**.
- Won't need **significant development** in near term.
- Suggest **don't try to convert** to ASP.NET Core.
- **Microsoft will support .NET Framework** for the foreseeable future.
- Windows itself **depends on it**.
- Payoff in converting **fringe applications** is unlikely to be **worth the effort**.

### When to convert
- **Best opportunity**: start on **small new greenfield projects**.
- Rather than **existing applications**.
- If existing application is **small**.
- Or will need **significant future development**.
- Porting may be a **good option**.

### Migration approach
- Always best to work in **small iterations** when porting.
- Rather than attempt to **convert entire application at once**.
- Microsoft provides **tools for that purpose**:
  - **System.Web adapters**
  - **YARP** (.NET-based reverse proxy; Yet Another Reverse Proxy)
  - **Visual Studio tooling**
- Help you implement the **strangler fig pattern**.
- Allows you to **migrate one page/API at a time**.
- **Reduces risk** associated with porting ASP.NET application to ASP.NET Core.
