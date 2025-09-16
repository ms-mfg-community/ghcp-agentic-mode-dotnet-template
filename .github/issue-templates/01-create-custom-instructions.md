---
title: "1 - Getting Started with Your New Repository"
labels: 
  - documentation
  - good first issue
  - setup
assignees: []
---

Welcome to your new repository created from the **ghcp-agentic-mode-dotnet-template**!

Create a c[ustom instructions](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions) file for the repository, with a heavy focus on Testing.

Specifics to keep in mind for testing:

- Isolation of Business Logic:
By using mocking (via NSubstitute), tests isolate the logic in services from external dependencies like repositories, ensuring tests only validate the code under test.

- Maintainable Test Data:
Factory classes such as PatronFactory and LoanFactory centralize test data creation, making tests easier to read, maintain, and update.

- Comprehensive Coverage:
Tests cover a wide range of scenarios, including success, error, and edge cases (e.g., membership expired, loan not found), improving reliability and robustness.

- Readability and Organization:
Tests are organized by domain (e.g., ApplicationCore/LoanService/ExtendLoan.cs), making it easy to locate and understand tests for specific features.

- Automated and Repeatable:
Using xUnit and .NET tooling, tests can be run automatically and repeatedly, supporting CI/CD and regression testing.

- Code Coverage Support:
Integration with Coverlet enables measurement of code coverage, helping identify untested code paths.

- Standard Tooling:
Leveraging widely-used frameworks (xUnit, NSubstitute) ensures compatibility, community support, and best practices.


