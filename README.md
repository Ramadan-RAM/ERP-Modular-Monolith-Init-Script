# ERP-Modular-Monolith-Init-Script
owerShell script to automate the creation of a clean .NET modular monolith solution with pre-defined layers (Domain, Application, Infrastructure, Presentation). Speeds up project setup with ready-to-use

NET Modular Monolith Solution Generator

This repository contains a PowerShell script that automates the creation of a clean .NET Modular Monolith solution.
The script sets up a ready-to-use project structure with the following layers:

Domain

Application

Infrastructure

Presentation

The goal is to speed up project setup by generating a standard architecture you can directly build upon.

🚀 Features

Generates a modular solution with a predefined folder and project structure.

Automatically links projects with correct references.

Clean and extensible base for enterprise applications.

Includes the Presentation layer (API/Front-end entry point).

📂 Generated Structure
YourSolutionName/
│
├── src/
│   ├── YourSolutionName.Domain/
│   ├── YourSolutionName.Application/
│   ├── YourSolutionName.Infrastructure/
│   ├── YourSolutionName.Presentation/
│
└── YourSolutionName.sln

⚡ How to Use

Clone this repository or download the script.

Open PowerShell in the script directory.

Run the script with your desired solution name:

.\Create-Solution.ps1 -SolutionName "MyProject"

🛠 Requirements

.NET 8 SDK (or higher)

PowerShell 5.1+

📌 Example
.\Create-Solution.ps1 -SolutionName "ERPSystem"
#
┌─────────────────────────────┐
│        ERP.Solution         │  (Visual Studio / dotnet sln)
└─────────────┬───────────────┘
              │
  ┌───────────┴──────────────────────────────────────────────────┐
  │                        SharedKernel                         │
  │  (ValueObjects, BaseEntities, Result<T>, Contracts, etc.)    │
  └───────────┬───────────┬───────────────────┬─────────────────┘
              │           │                   │
 ┌────────────▼───┐ ┌─────▼────────┐   ┌─────▼────────┐
 │   HR.BC        │ │   Users.BC   │   │  Finance.BC  │   … 
 │  ───────────── │ │──────────────│   │──────────────│
 │  HR.Presentation││Users.Presentation││Finance.Presentation│
 │  HR.Application ││Users.Application ││Finance.Application │
 │  HR.Domain     │ │Users.Domain     │ │Finance.Domain     │
 │  HR.Infrastructure│Users.Infrastructure│Finance.Infrastructure│
 └────────────────┘ └──────────────┘   └────────────────┘

              ▲             ▲                    ▲
              │   Domain Events / MediatR        │
              └─────────────┴────────────────────┘
                         EventBus (RabbitMQ / Outbox)



This will create a solution called ERPSystem with all required layers already connected.
