---
title: "3 - Customize .NET Template for Your Project and build Unit Testing Framework"
labels:
  - setup
  - template
  - customization
  - dotnet
assignees: []
---

This repository was created from the `ghcp-agentic-mode-dotnet-template`. Follow this guide to customize it for your specific needs.

## 📋 Customization Checklist

### Solution and Project Structure
- [ ] Rename the solution file (`.sln`) to match your project name
- [ ] Update all project files (`.csproj`) with appropriate names
- [ ] Update `<RootNamespace>` and `<AssemblyName>` in project files
- [ ] Replace all namespace declarations throughout the codebase
- [ ] Update package references to latest stable versions

### Configuration Files
- [ ] Update `appsettings.json` with your application settings
- [ ] Configure `appsettings.Development.json` for local development
- [ ] Set up environment-specific configuration files
- [ ] Update connection strings and API endpoints
- [ ] Configure logging settings

### Steps
Build a Unit Testing GitHub Actions Pipeline

Ensure the check can run every time a Push or PR into the Main Branch occurs, and fail on any tests that do not pass

All unit tests for the project should be run
Analyze existing tests, consider adding separate jobs for each testing type, suite, or project in the solution that is tested
Utilize Existing instructions files for specifics on Testing

---
*This issue was automatically created when the repository was generated from a template.*
