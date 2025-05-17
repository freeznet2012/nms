# Newspaper Management System (NMS)

A comprehensive solution for newspaper distribution agencies to manage their operations, customers, routes, and finances efficiently.

## Overview

The Newspaper Management System (NMS) is designed to streamline the operations of newspaper distribution businesses. It helps newspaper agents manage their customer base, delivery routes, subscriptions, billing, and payments from a single platform.

## Core Features

### For Newspaper Agents (Owners)
- **Customer Management**
  - Add, edit, and manage customer profiles
  - View customer history and subscription details
  - Track customer interactions and complaints
  
- **Route Management**
  - Create and optimize delivery routes
  - Assign customers to specific routes
  - Generate route maps and delivery instructions
  
- **Newspaper Management**
  - Maintain catalog of available newspapers and magazines
  - Track pricing and publication frequency
  - Manage special editions and supplements
  
- **Subscription Management**
  - Create and manage customer subscriptions
  - Handle temporary stops, address changes, and special delivery instructions
  - Support for daily, weekly, monthly subscription models
  
- **Invoicing & Billing**
  - Generate periodic invoices (monthly/quarterly)
  - Apply discounts and special offers
  - Track invoice status and payment history
  
- **Payment Processing**
  - Record and track payments from customers
  - Support multiple payment methods
  - Generate payment receipts and reports
  
- **Reporting & Analytics**
  - Business performance dashboards
  - Route efficiency metrics
  - Financial reports and projections

### For Customers
- View subscription details
- Access billing history
- Make online payments
- Request delivery changes or pause service
- Submit feedback or complaints

### For Admins
- User management and access control
- System configuration and maintenance
- Master data management
- Audit trails and system logs

## Technical Stack

- **Backend**
  - .NET 8+ with ASP.NET Core Web API
  - Entity Framework Core for ORM
  - SQL Server for database
  - Identity Server for authentication/authorization
  - SignalR for real-time updates (optional)

- **Frontend**
  - Angular 17
  - TypeScript
  - Angular Material UI components
  - RxJS for reactive programming
  - NgRx for state management (optional)

- **DevOps & Infrastructure**
  - Docker for containerization
  - GitHub Actions for CI/CD
  - Azure for cloud hosting

## Development Milestones

### Phase 1: Foundation (Weeks 1-4)
- [ ] Project setup and architecture
- [ ] Database design and implementation
- [ ] Authentication and authorization system
- [ ] Basic CRUD operations for customer and newspaper management

### Phase 2: Core Functionality (Weeks 5-8)
- [ ] Route management and optimization
- [ ] Subscription management system
- [ ] Basic invoicing functionality
- [ ] Simple reporting system

### Phase 3: Financial Operations (Weeks 9-12)
- [ ] Complete billing and invoicing features
- [ ] Payment processing and tracking
- [ ] Financial reporting and statements
- [ ] Customer payment portal

### Phase 4: Advanced Features (Weeks 13-16)
- [ ] Analytics and business intelligence
- [ ] Route optimization algorithms
- [ ] Mobile-responsive design
- [ ] Notification system (email, SMS)

### Phase 5: Finalization (Weeks 17-20)
- [ ] System integration and testing
- [ ] Performance optimization
- [ ] User documentation
- [ ] Deployment preparation

## Getting Started

### Prerequisites
- .NET 8 SDK
- Node.js and npm
- SQL Server
- Visual Studio 2022 or VS Code

### Installation
1. Clone the repository
2. Navigate to the backend directory and run `dotnet restore`
3. Navigate to the frontend directory and run `npm install`
4. Configure the database connection in `appsettings.json`
5. Run database migrations using `dotnet ef database update`
6. Start the backend with `dotnet run`
7. Start the frontend with `ng serve`

## Project Structure

### Backend Project Structure (NMS.Backend)

The backend follows a simplified three-layer architecture:

```
NMS.Backend/
│
├── src/
│   ├── NMS.API/                  # ASP.NET Core Web API
│   │   ├── Controllers/          # API Controllers
│   │   │   ├── CustomerController.cs
│   │   │   ├── NewspaperController.cs
│   │   │   ├── RouteController.cs
│   │   │   ├── SubscriptionController.cs
│   │   │   ├── InvoiceController.cs
│   │   │   └── PaymentController.cs
│   │   │
│   │   ├── Filters/              # Action filters
│   │   ├── Middlewares/          # Custom middlewares
│   │   ├── DTOs/                 # Data Transfer Objects
│   │   ├── Mappings/             # AutoMapper profiles
│   │   └── Program.cs            # Application entry point
│   │
│   ├── NMS.Core/                 # Core layer (Domain + Application logic)
│   │   ├── Entities/             # Domain entities
│   │   │   ├── Customer.cs
│   │   │   ├── Newspaper.cs
│   │   │   ├── Route.cs
│   │   │   ├── Subscription.cs
│   │   │   ├── Invoice.cs
│   │   │   └── Payment.cs
│   │   │
│   │   ├── Interfaces/           # Interfaces for repositories and services
│   │   │   ├── Repositories/     # Repository interfaces
│   │   │   └── Services/         # Service interfaces
│   │   │
│   │   ├── Services/             # Business logic services
│   │   │   ├── CustomerService.cs
│   │   │   ├── NewspaperService.cs
│   │   │   ├── RouteService.cs
│   │   │   ├── SubscriptionService.cs
│   │   │   ├── InvoiceService.cs
│   │   │   └── PaymentService.cs
│   │   │
│   │   ├── Exceptions/           # Custom exceptions
│   │   └── Helpers/              # Helper classes and extensions
│   │
│   └── NMS.Infrastructure/       # Infrastructure layer
│       ├── Data/                 # Data access
│       │   ├── NMSDbContext.cs   # EF Core DbContext
│       │   ├── EntityConfigurations/ # Entity type configurations
│       │   └── Migrations/       # EF Core Migrations
│       │
│       ├── Repositories/         # Repository implementations
│       │   ├── CustomerRepository.cs
│       │   ├── NewspaperRepository.cs
│       │   ├── RouteRepository.cs
│       │   ├── SubscriptionRepository.cs
│       │   ├── InvoiceRepository.cs
│       │   └── PaymentRepository.cs
│       │
│       ├── Services/             # External service implementations
│       ├── Identity/             # Authentication/Authorization
│       └── DependencyInjection.cs # Infrastructure services registration
│
└── tests/
    ├── NMS.API.Tests/            # API layer tests
    ├── NMS.Core.Tests/           # Core layer tests
    └── NMS.Infrastructure.Tests/ # Infrastructure layer tests
```

### Frontend Project Structure (Angular)

```
nms-frontend/
│
├── src/
│   ├── app/
│   │   ├── core/                 # Core module
│   │   │   ├── auth/             # Authentication
│   │   │   ├── guards/           # Route guards
│   │   │   ├── http/             # HTTP interceptors
│   │   │   ├── services/         # Core services
│   │   │   └── core.module.ts
│   │   │
│   │   ├── shared/               # Shared module
│   │   │   ├── components/       # Shared components
│   │   │   ├── directives/       # Custom directives
│   │   │   ├── pipes/            # Custom pipes
│   │   │   ├── models/           # Shared models/interfaces
│   │   │   └── shared.module.ts
│   │   │
│   │   ├── features/             # Feature modules
│   │   │   ├── dashboard/        # Dashboard feature
│   │   │   ├── customers/        # Customers management
│   │   │   ├── newspapers/       # Newspaper management
│   │   │   ├── routes/           # Route management
│   │   │   ├── subscriptions/    # Subscription management
│   │   │   ├── invoices/         # Invoice management
│   │   │   ├── payments/         # Payment management
│   │   │   ├── reports/          # Reports and analytics
│   │   │   └── admin/            # Admin features
│   │   │
│   │   ├── layouts/              # Layout components
│   │   │   ├── main-layout/      # Main application layout
│   │   │   ├── auth-layout/      # Authentication layout
│   │   │   └── customer-layout/  # Customer portal layout
│   │   │
│   │   ├── app-routing.module.ts # Main routing configuration
│   │   ├── app.component.ts      # Root component
│   │   └── app.module.ts         # Root module
│   │
│   ├── assets/                   # Static assets
│   │   ├── images/
│   │   ├── icons/
│   │   └── styles/               # Global styles
│   │
│   ├── environments/             # Environment configurations
│   │   ├── environment.ts
│   │   └── environment.prod.ts
│   │
│   ├── index.html                # Main HTML file
│   ├── main.ts                   # Application bootstrap
│   └── styles.scss               # Global styles
│
├── angular.json                  # Angular CLI configuration
├── package.json                  # NPM dependencies
├── tsconfig.json                 # TypeScript configuration
└── karma.conf.js                 # Test runner configuration
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.