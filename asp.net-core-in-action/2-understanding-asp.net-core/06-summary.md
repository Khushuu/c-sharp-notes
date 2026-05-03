# Summary

## Key takeaways

- **Web frameworks** provide a way to build **dynamic web applications easily**.
- **ASP.NET Core** is a web framework built with **modern software architecture practices** and **modularization** as its focus.
- **ASP.NET Core runs** on the **cross-platform .NET 7 platform**.
- You can access **Windows-specific features** such as the **Windows Registry**.
- Use the **Windows Compatibility Pack** for this purpose.

## .NET versions

- **.NET 5, .NET 6, and .NET 7** are the **next versions** of .NET Core after .NET Core 3.1.

## Best practices

- **ASP.NET Core** is best used for **new greenfield projects**.
- **Legacy technologies** such as **WCF Server** and **Web Forms** can't be used directly.
- They have **analogues** and **supporting libraries** that can help with **porting ASP.NET applications**.

## Migration strategy

- You can **convert an existing ASP.NET application** to **ASP.NET Core gradually**.
- Use the **strangler fig pattern**.
- Use **tooling** and **libraries provided by Microsoft**.

## Deployment considerations

- **ASP.NET Core apps** are often **protected from the internet** by a **reverse-proxy server**.
- The reverse proxy **forwards requests** to the application.
