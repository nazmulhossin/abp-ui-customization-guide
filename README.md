# ABP UI Customization Guide

The ABP Framework provides a powerful, enterprise-grade infrastructure for building modern web applications. By default, an ABP Angular application comes with the LeptonX Lite theme, which offers a clean and functional UI out of the box. However, real-world projects often require custom styling, third-party component libraries, or even a completely redesigned user interface.

This repository provides a practical, step-by-step guide for customizing the UI of an **ABP Angular application**. It focuses on modern frontend tools and techniques to enhance the default ABP UI experience, making it more flexible, scalable, and visually appealing.

The goal of this guide is to help developers move beyond the default UI and build **custom, production-ready interfaces** using popular UI frameworks and styling solutions.

This guide is divided into separate documents, each focusing on a specific customization area:

1. Add **Tailwind CSS** to ABP Angular  ([Read](./docs/add-tailwind-css-to-abp-angular.md))
2. Add **PrimeNG** to ABP Angular  ([Read](./docs/add-primeng-to-abp-angular.md))
3. Replace the **ABP Default Theme**  ([Read](./docs/replace-abp-theme-with-custom-theme.md))

Each topic is explained in separate, detailed documents, so you can follow them independently or in any order.

This overview serves as the foundation for the entire guide, covering the project setup, prerequisites, and providing a clear roadmap for the series.

## Project Setup Used in This Guide

To keep things consistent and easy to follow, all examples in this guide are built using:

- **ABP Layered Application (free/community edition)**
- **Angular UI**
- **Entity Framework Core**
- **PostgreSQL**

> 💡 Although we use this specific setup, the concepts in this guide can be applied to **any ABP-based project**.


## Prerequisites

Before starting any of the practical guides, ensure your local machine has the following installed:

- **.NET SDK** (10.0 or later)
- **Node.js** (v18 or later) & npm/yarn/pnpm
- **Angular CLI** (globally installed: `npm install -g @angular/cli`)
- **ABP CLI** (globally installed: `dotnet tool install -g Volo.Abp.Studio.Cli`)
- **PostgreSQL** (running locally with `postgres` user and password)
- **A code editor** (VS Code, Visual Studio 2022+, or Rider)
- **Git** (for cloning the final repository)

## Create the Practice Project from Scratch

To follow along with the guide, you can create a fresh ABP project using the command below:

```bash
abp new Acme.BookStore -u angular -dbms PostgreSQL -m none --theme leptonx-lite -csf -scp --connection-string "Host=localhost;Port=5432;Database=BookStore;User ID=postgres;Password=your_password;"
```
## Run This Repository Locally

To run the project from this repository on your local machine, follow these steps:

#### 1. Clone the Repository

```bash
git clone https://github.com/nazmulhossin/abp-ui-customization-guide.git
```
#### 2. Navigate to the Project Root
```bash
cd abp-ui-customization-guide/Acme.BookStore
```
#### 3. Install ABP Client Libraries
ABP uses a custom system for managing client-side dependencies. Run the following command in the root of the `Acme.BookStore` solution (where the `.slnx` file exists):
```bash
abp install-libs
```
#### 4. Run the application
- Run the `.DbMigrator` project to apply database migrations and run the  `.HttpApi.Host` project.
- Start the Angular application (`ng serve` or `yarn start` inside the angular folder)

## Structure of This Repository

Each topic is documented separately for clarity and scalability. Every guide includes its own **independent Angular project**, allowing you to experiment without affecting other setups.

```
├── Acme.BookStore
│ ├── angulars
│ │ ├── tailwind-demo
│ │ ├── primeng-demo
│ │ ├── theme-replacement-demo
│ │ └── ...
│ │
│ ├── src
│ │ ├── Acme.BookStore.Application
│ │ ├── Acme.BookStore.Application.Contracts
│ │ ├── Acme.BookStore.DbMigrator
│ │ ├── Acme.BookStore.Domain
│ │ ├── Acme.BookStore.Domain.Shared
│ │ ├── Acme.BookStore.EntityFrameworkCore
│ │ ├── Acme.BookStore.HttpApi
│ │ ├── Acme.BookStore.HttpApi.Client
│ │ └── Acme.BookStore.HttpApi.Host
│ │
│ ├── test
│ └── Acme.BookStore.slnx
│
├── docs
│ ├── tailwind-integration.md
│ ├── primeng-integration.md
│ └── theme-replacement.md
│
└── README.md
```
All Angular projects are organized under a single `angulars` folder. To create this structure:
- Create a folder named `angulars` inside the `Acme.BookStore` directory.
- Copy the default Angular project into `angulars`.
- Rename it based on the specific guide.

Each project is completely independent and used only for its corresponding documentation.
