# mvcwebapp

ASP.NET Core MVC Web Application by .NET 10 serving CRUD of Employees towards a MS SQL Database

Last updated

- 13-11-2025

# Create a global json

dotnet new globaljson --sdk-version 10.0.100 --force

# Updated the EF global tool from 8 to 10

Verify the version:

- dotnet ef

Install to the newest version globally:

- dotnet tool update --global dotnet-ef

Now verify again by dotnet ef

It is possible to install the tool locally in the project by:

- dotnet tool update dotnet-ef

# Create the remote MS SQL DB

- If the folder "Migrations" do not exist or is empty run: 

dotnet ef migrations add FirstCreate --output-dir Migrations/SqlServerMigrations

- If the folder "Migrations" exist or have migration files run: dotnet ef database update

# Functionality of the Web App

- CRUD functionality
- Display a list of Employees

# Tech used for creating the Web App

- A .NET 10 MVC Web App
- A traditional Webhotel for hosting
- VS Code

# Development

dotnet run

# Production

Create a self contained build for production at the remote server / traditionel web hotel

dotnet publish mvcwebapp.csproj --configuration Release --runtime win-x86 --self-contained

Upload the build to remote server

At my remote servers the web.config needs to be without the folowing:

hostingModel="inprocess"

# Test the Web App - The Employees

- yourhost/employee

# Tip and Tricks

When loading Razor files I have had an issue dealing with a popup msg in VS Code:

"Request textDocument/inlayHint failed. Message: Razor source generator is not ... referenced Code: -32000 ... "

To prevent the msg to show up I uninstalled the VS Code extentions:

- C# Dev Kit

- C#

- .NET install Tool

Then closed VS Code and deleted the obj and bin and opened VS Code and installed the extentions again

I changed settings in the C# extention like below:

- Extentions - C# - LSP Server - Dotnet Server - Enabled the "Supress LSP Error Toast" - Restart VS Code

Finally I deleted the extention cache "csdevkit" by the path:

- C: Users \ .vscode \ extensions \ csdevkit

Restart VS Code

Thats it :-)







