# Why ASP.NET Core Was Created

## Five main goals for ASP.NET Core
- **Run and develop cross-platform**
- **Modular architecture** for easier maintenance
- **Completely open-source** software
- **Adhere to web standards**
- **Applicable to current trends** in web development (client-side apps, cloud deployment)

## The platform requirement
- To achieve these goals, Microsoft needed a platform providing underlying libraries.
- Required capabilities:
  - Creating basic objects such as **lists and dictionaries**
  - Performing basic file operations
- Previous ASP.NET was tied to **Windows-only .NET Framework**.
- This dependency prevented cross-platform development.

## .NET Core creation
- Microsoft created a **lightweight platform** for cross-platform support.
- The platform runs on **Windows, Linux, and macOS**.
- Called **.NET Core** (subsequently renamed to just **.NET**)

## .NET 5+ unification
- **.NET 5** was the next version after .NET Core 3.1.
- Followed by **.NET 6** and **.NET 7**.
- Represents a **unification of .NET Core and other .NET platforms**.
- Provides a **single runtime and framework**.
- Considered the **future of .NET**.
- Microsoft dropped the **\"Core\"** from the name for .NET 5+.

## Technical distinctions
- .NET Core and .NET 5+ employ **many of the same APIs as .NET Framework**.
- More **modular** than .NET Framework.
- Implements a **different set of features** from .NET Framework.
- Goal: provide a **simpler programming model** and **modern APIs**.
- It is a **separate platform** rather than a fork of .NET Framework.
- Uses similar code for many APIs, but is architecturally distinct.

## About .NET terminology
- **Term: .NET 5+** refers to .NET 5, .NET 6, and .NET 7.
- **Term: .NET Core** refers to previous versions before .NET 5.

## Benefits and limitations of legacy ASP.NET
- **First ASP.NET released:** June 2002 as part of .NET Framework 1.0.
- **ASP.NET Web Forms** introduced a graphical designer and event model.
- Allowed developers to build web applications rapidly.
- Mirrored desktop application-building techniques.

## Evolution to ASP.NET MVC
- Over time, the web development ecosystem changed.
- ASP.NET Web Forms suffered from problems in larger applications:
  - **Lack of testability**
  - **Complex stateful model**
  - **Limited influence on generated HTML** (making client-side development difficult)
- Developers began evaluating other options.
- **First version of ASP.NET MVC released:** 2009
- Based on **Model-View-Controller (MVC)** pattern.
- Used in frameworks such as Ruby on Rails, Django, and Java Spring.
- MVC allowed developers to:
  - **Separate UI elements from application logic**
  - Make **testing easier**
  - Provide **tighter control of HTML generation**

## The System.Web.dll dependency
- All ASP.NET MVC iterations were built on **System.Web.dll**.
- This library is part of **.NET Framework** and comes preinstalled with Windows.
- Contains **all core code** that ASP.NET uses when building applications.

## Advantages of System.Web.dll
- **Reliable, battle-tested platform** for Windows web applications.
- Provides a **wide range of features** in production for many years.
- **Well known** by virtually all Windows web developers.

## Disadvantages of System.Web.dll
- Changes to System.Web.dll are **far-reaching and slow to roll out**.
- Limits the extent to which ASP.NET can evolve.
- Results in **release cycles happening only every few years**.
- **Explicit coupling with Windows web host (IIS)**.
- Precludes use on non-Windows platforms.

## Legacy ASP.NET status
- Microsoft declared **.NET Framework to be \"done.\"**
- Will not be removed or replaced.
- Will not receive **any new features**.
- ASP.NET based on System.Web.dll won\u2019t receive new features or updates either.

## Modern web framework trends
- Many web developers started looking at **cross-platform web frameworks**.
- Frameworks can run on **Windows, Linux, and macOS**.
- Microsoft felt the time had come to create a **framework no longer tied to Windows legacy**.
- **ASP.NET Core was born** as a result.

## ASP.NET Core architecture
- With .NET 7, possible to build **console applications** that run cross-platform.
- ASP.NET Core is an **additional layer on top of console applications**.
- Converting to a web application involves **adding and composing libraries**.
- Adding a **web server library** converts a console app to an ASP.NET Core web app.
- Other features like **configuration** and **logging** are added using various libraries.

## ASP.NET Core API design
- ASP.NET Core contains a huge number of APIs.
- You rarely need all available features.
- Some features are **built in** and appear in virtually every application:
  - Reading configuration files
  - Performing logging
- Other features are **provided by separate libraries**.
- Built on top of base capabilities for **application-specific functionality**.
  - Third-party logins via Facebook or Google

## Open-source libraries
- Most libraries and APIs used in ASP.NET Core are available on **GitHub**.
- Located in the **Microsoft .NET organization repositories** at https://github.com/dotnet/aspnetcore.
- Core APIs available:
  - **Authentication APIs**
  - **Logging APIs**
  - Many **peripheral libraries** (third-party authentication libraries)

## ASP.NET Core design philosophy
- All ASP.NET Core applications follow a similar design for **basic configuration**.
- Framework is **flexible**, leaving you free to create your own code conventions.
- These common APIs and design conventions are covered by the term **ASP.NET Core**.
