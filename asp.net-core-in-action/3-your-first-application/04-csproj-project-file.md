# The .csproj Project File

## Purpose

- Contains details required for .NET tooling to **build your project**
- Defines:
  - Type of project (web app, console app, library)
  - Target platform (.NET Core 3.1, .NET 7, etc.)
  - NuGet package dependencies

## Modern .csproj Improvements

- **No GUIDs** — Globally unique identifiers rarely used now
- **Implicit file includes** — Files automatically included in build (no manual listing)
- **No paths to NuGet .dll files** — Reference packages directly without specifying disk paths

## Basic .csproj Structure

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net7.0</TargetFramework>
    <Nullable>enable</Nullable>
    <ImplicitUsings>enable</ImplicitUsings>
  </PropertyGroup>
</Project>

Key Elements

Element	Description

Sdk attribute	Specifies project type, includes default build settings
TargetFramework	Framework to run on (net6.0, net7.0)
Nullable	Enables C# 8 nullable reference types
ImplicitUsings	Enables C# 10 implicit using statements


Adding NuGet Packages
dotnet add package Newtonsoft.Json

Result in .csproj
<ItemGroup>
  <PackageReference Include="NewtonSoft.Json" Version="13.0.1" />
</ItemGroup>