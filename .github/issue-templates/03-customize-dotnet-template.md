---
title: "🔧 Customize .NET Template for Your Project"
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

### CI/CD Pipeline
- [ ] Review and update `.github/workflows/` files
- [ ] Configure build and test workflows for your needs
- [ ] Set up deployment workflows
- [ ] Add necessary secrets to GitHub repository settings
- [ ] Configure code coverage and quality gates

### Dependencies and Packages
```bash
# Update all NuGet packages
dotnet list package --outdated
dotnet add package [PackageName] --version [Version]
```

- [ ] Review all NuGet package dependencies
- [ ] Remove unused packages
- [ ] Add project-specific packages
- [ ] Update to latest stable versions where appropriate
- [ ] Document any version constraints

### Code Cleanup
- [ ] Remove template-specific example code
- [ ] Delete unused controllers, services, or models
- [ ] Clean up example API endpoints
- [ ] Remove or update sample data and seeds
- [ ] Update or remove template-specific tests

### Docker Configuration (if applicable)
- [ ] Update `Dockerfile` with correct project paths
- [ ] Configure `docker-compose.yml` for your services
- [ ] Set appropriate base images
- [ ] Configure environment variables
- [ ] Set up health checks

### Security Configuration
- [ ] Update CORS policies for your domains
- [ ] Configure authentication and authorization
- [ ] Set up proper secret management
- [ ] Review and update security headers
- [ ] Configure HTTPS/TLS settings

### Database Setup (if applicable)
- [ ] Update Entity Framework migrations
- [ ] Configure database providers
- [ ] Set up initial data migrations
- [ ] Configure connection resilience
- [ ] Document database schema

## 🛠️ Useful Commands

```bash
# Rename namespaces across the solution (PowerShell)
Get-ChildItem -Recurse -Filter *.cs | ForEach-Object {
    (Get-Content $_.FullName) -replace 'OldNamespace', 'NewNamespace' | 
    Set-Content $_.FullName
}

# Update project references
dotnet sln rename-project OldName NewName

# Clean and rebuild
dotnet clean
dotnet restore
dotnet build
```

## 📚 Additional Resources

- [.NET Project Structure Best Practices](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures)
- [ASP.NET Core Documentation](https://docs.microsoft.com/en-us/aspnet/core/)
- [Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/)
- [.NET CLI Reference](https://docs.microsoft.com/en-us/dotnet/core/tools/)

## ✅ Definition of Done

This issue can be closed when:
- [ ] All template references have been replaced
- [ ] Project builds successfully with no warnings
- [ ] All tests pass
- [ ] Documentation has been updated
- [ ] CI/CD pipelines run successfully
- [ ] Application runs locally as expected

---
*This issue was automatically created when the repository was generated from a template.*