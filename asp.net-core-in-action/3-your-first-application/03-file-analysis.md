
## Key Files and Folders

### WebApplication1.csproj
- **Most important file** in the project
- Describes how to build the project
- Lists required NuGet packages
- Edit by double-clicking project name in Solution Explorer

### Properties/launchSettings.json
- Controls how Visual Studio runs and debugs the application
- Shown as special node in Solution Explorer (out of alphabetical order)

### appsettings.json Files
- Provide **configuration settings** used at runtime
- Control app behavior (e.g., database connection strings)
- `appsettings.Development.json` for development-specific settings

### Program.cs
- Configures and runs the application
- Contains application startup code

## Visual Studio Special Nodes

| Node | Description |
|------|-------------|
| **Dependencies** | Shows all NuGet packages and dependencies |
| **Connected Services** | Shows remote services the project relies on |

- These nodes don't have corresponding folders on disk
