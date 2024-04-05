## Where are binaries located?

When building in Visual Studio UI, or `dotnet build` from command line in the root project directory, or in VS Code using C# Dev Kit extension, 
* {Project}\bin\ARM64\Debug\net8.0

When building using `dotnet build` from command line in the project directory:
* {Project}\bin\Debug\net8.0

When building using `dotnet build -a arm64`
* {Project}\bin\Debug\net8.0\win-arm64\

PROBLEM: C# dev kit will only discover tests if they are built into {Project}\bin\ARM64\Debug\net8.0. However, I can't cause this from the command line within a project. I guess I could just *not* build from with a directory,
and ALWAYS build from above.

Ok, the trick is `dotnet build -p:platform=arm64`
