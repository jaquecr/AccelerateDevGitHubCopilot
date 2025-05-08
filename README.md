# Library App

## Description
Library App is a console-based library management system that allows users to manage patrons, book loans, and memberships. It provides functionality to search for patrons, view their details, renew memberships, and manage book loans (e.g., extend or return loans). The application is built using a modular architecture with a focus on separation of concerns, testability, and extensibility.

## Project Structure
- `AccelerateDevGitHubCopilot.sln` - Solution file for the project.
- `README.md` - Documentation for the project.
- `src/`
  - `Library.ApplicationCore/` - Contains core business logic, entities, enums, and interfaces.
    - `Entities/` - Domain models such as `Patron`, `Loan`, `Book`, etc.
    - `Enums/` - Enumerations for statuses and helper utilities.
    - `Interfaces/` - Interfaces for services and repositories.
    - `Services/` - Core services like `PatronService` and `LoanService`.
    - `Library.ApplicationCore.csproj` - Project file for the core library.
  - `Library.Console/` - Contains the console application logic.
    - `ConsoleApp.cs` - Main application class implementing the state machine.
    - `ConsoleState.cs` - Enum defining application states.
    - `CommonActions.cs` - Enum defining user actions.
    - `Program.cs` - Entry point for the console application.
    - `Json/` - Sample JSON data for authors, books, patrons, and loans.
    - `appSettings.json` - Configuration file for JSON data paths.
    - `Library.Console.csproj` - Project file for the console application.
  - `Library.Infrastructure/` - Contains infrastructure code for data access.
    - `Data/` - JSON-based repositories for patrons and loans.
    - `Library.Infrastructure.csproj` - Project file for the infrastructure library.
- `tests/`
  - `UnitTests/` - Contains unit tests for the application.
    - `ApplicationCore/` - Tests for core services like `PatronService` and `LoanService`.
    - `LoanFactory.cs` - Factory for creating test loan objects.
    - `PatronFactory.cs` - Factory for creating test patron objects.
    - `UnitTests.csproj` - Project file for unit tests.

## Key Classes and Interfaces
### Core Classes
- `Patron` - Represents a library patron with membership details and loans.
- `Loan` - Represents a book loan with due dates and return status.
- `Book` - Represents a book with metadata like title, author, and genre.
- `BookItem` - Represents a physical copy of a book.

### Enums
- `MembershipRenewalStatus` - Statuses for membership renewal (e.g., `Success`, `TooEarlyToRenew`).
- `LoanReturnStatus` - Statuses for returning a loan (e.g., `Success`, `AlreadyReturned`).
- `LoanExtensionStatus` - Statuses for extending a loan (e.g., `Success`, `LoanExpired`).

### Interfaces
- `IPatronRepository` - Defines methods for accessing patron data.
- `ILoanRepository` - Defines methods for accessing loan data.
- `IPatronService` - Defines methods for managing patron memberships.
- `ILoanService` - Defines methods for managing book loans.

### Console Application
- `ConsoleApp` - Implements the state machine for the console application.
- `ConsoleState` - Enum defining application states (e.g., `PatronSearch`, `LoanDetails`).
- `CommonActions` - Enum defining user actions (e.g., `Select`, `Quit`).

### Infrastructure
- `JsonPatronRepository` - JSON-based implementation of `IPatronRepository`.
- `JsonLoanRepository` - JSON-based implementation of `ILoanRepository`.
- `JsonData` - Handles loading and saving JSON data.

## Usage
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>

