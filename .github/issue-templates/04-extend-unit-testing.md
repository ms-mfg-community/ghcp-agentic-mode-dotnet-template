---
title: "👨‍💻 Extend Unit Testing"
labels:
  - developer-experience
  - workflow
  - standards
  - team
assignees: []
---

**Goal:** Extend the UnitTests project to begin testing methods in the Library.Infrastructure project

- Test Project Structure:
All unit tests are located in the [UnitTests](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) folder, with domain-specific tests organized under subfolders like ApplicationCore/LoanService and ApplicationCore/PatronService.

- Test Factories:

Test data is generated using factory classes such as [LoanFactory](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) and [PatronFactory](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html), which provide methods to create domain entities in various states for testing.

- Mocking Dependencies:

The tests use NSubstitute to mock repository interfaces (e.g., [ILoanRepository](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html), [IPatronRepository](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)), allowing isolation of the service logic from data access concerns.

- Test Methods:

Each test class (e.g., [ExtendLoanTest](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html), [RenewMembershipTest](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)) contains multiple [Fact]-decorated methods, each verifying a specific scenario or business rule.

- Assertions:

Tests assert expected outcomes using xUnit's [Assert](vscode-file://vscode-app/c:/Users/codycarlson/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) methods, checking both status enums and state changes on domain entities.

- Test Execution:

Tests are run using the command:
```
dotnet test tests/UnitTests/UnitTests.csproj
```

## 📐 Coding Standards

### C# Conventions
```csharp
// Example of preferred patterns
public interface IUserService
{
    Task<User> GetUserAsync(int userId, CancellationToken cancellationToken);
}

public class UserService : IUserService
{
    private readonly ILogger<UserService> _logger;
    private readonly IUserRepository _userRepository;

    public UserService(ILogger<UserService> logger, IUserRepository userRepository)
    {
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
        _userRepository = userRepository ?? throw new ArgumentNullException(nameof(userRepository));
    }

    public async Task<User> GetUserAsync(int userId, CancellationToken cancellationToken)
    {
        // Implementation
    }
}
```

### Documentation Standards
- [ ] XML documentation for all public APIs
- [ ] README files for each major component
- [ ] Architecture decision records (ADRs)
- [ ] API documentation generation
- [ ] Code examples and samples

## 🧪 Testing Strategy

### Test Organization
- [ ] Unit tests in `*.Tests` projects
- [ ] Integration tests in `*.IntegrationTests` projects
- [ ] End-to-end tests setup
- [ ] Test naming conventions
- [ ] Test data management strategy

### Coverage Requirements
- [ ] Set minimum code coverage percentage
- [ ] Configure coverage reporting
- [ ] Exclude generated code from coverage
- [ ] Set up coverage gates in CI/CD
- [ ] Document testing best practices

## 🚀 Productivity Tools

### Recommended IDE Extensions
- [ ] GitHub Copilot
- [ ] Code analyzers
- [ ] Test runners
- [ ] Docker support
- [ ] Git integration enhancements

### Development Scripts
```json
// Add to package.json or create PowerShell/Bash scripts
{
  "scripts": {
    "build": "dotnet build",
    "test": "dotnet test",
    "watch": "dotnet watch run",
    "format": "dotnet format",
    "clean": "dotnet clean && rm -rf **/bin **/obj"
  }
}
```

## 📋 Team Onboarding

### Developer Checklist
- [ ] Access to repository
- [ ] Development environment setup guide
- [ ] Required tools installation list
- [ ] Access to documentation
- [ ] Pair programming session scheduled

### Documentation Needed
- [ ] Getting started guide
- [ ] Architecture overview
- [ ] Development environment setup
- [ ] Troubleshooting guide
- [ ] FAQ document

## 🎯 Success Metrics

- [ ] All team members following conventions
- [ ] Consistent code style across repository
- [ ] Reduced PR review cycles
- [ ] Improved code quality metrics
- [ ] Faster onboarding for new developers

---
*This issue was automatically created when the repository was generated from a template.*
