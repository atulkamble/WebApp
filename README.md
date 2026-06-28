# 🚀 Deploy a Blazor .NET Web Application to Azure App Service

This project demonstrates how to deploy a **Blazor (.NET) Web Application** from **GitHub** to **Azure App Service** using **Deployment Center (GitHub Integration)**.

**Repository:** `https://github.com/atulkamble/WebApp`

---

# 📌 Architecture

```text
Visual Studio
      │
      ▼
Create Blazor App
      │
      ▼
GitHub Repository
      │
      ▼
Azure Deployment Center
      │
      ▼
Azure App Service
      │
      ▼
Live Website
```

---

# 📋 Prerequisites

* Azure Subscription
* GitHub Account
* Windows Server 2025 Datacenter
* RDP Access
* Internet Connection

---

# 🖥️ Step 1 - Create Windows Server VM

Create a Windows Server VM.

**Operating System**

```
Windows Server 2025 Datacenter
```

Connect using **Remote Desktop (RDP).**

---

# 🔐 Step 2 - Disable Internet Explorer Enhanced Security

Open

```
Server Manager
```

Go to

```
Local Server
```

Disable

```
IE Enhanced Security Configuration

Administrators : OFF
Users          : OFF
```

---

# 🛠️ Step 3 - Install Required Software

Install Chocolatey first.

Open **PowerShell as Administrator**

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
```

```powershell
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072
```

```powershell
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Verify

```powershell
choco --version
```

---

## Install Git

```powershell
choco install git -y
```

Verify

```powershell
git --version
```

---

## Install Python

```powershell
choco install python -y
```

Verify

```powershell
python --version
```

---

## Install Azure CLI

```powershell
choco install azure-cli -y
```

Verify

```powershell
az version
```

---

## Install .NET SDK

```powershell
choco install dotnet -y
```

Verify

```powershell
dotnet --version
```

---

## Install Visual Studio 2022 Community

Download

https://visualstudio.microsoft.com/downloads/

Install workload

```
ASP.NET and Web Development
```

---

## Install GitHub Desktop

Download

https://desktop.github.com/

---

# ✅ Verify Installed Software

```powershell
git --version

python --version

dotnet --version

az version

choco --version
```

---

# 💻 Step 4 - Create Blazor Application

Open

```
Visual Studio
```

Select

```
Create New Project
```

Search

```
Blazor Web App
```

Click

```
Next
```

Project Name

```
WebApp
```

Framework

```
.NET 10
```

Click

```
Create
```

---

# ▶️ Step 5 - Run the Application

Press

```
F5
```

or

```
Ctrl + F5
```

Verify the application opens in your browser.

---

# 📂 Step 6 - Push Project to GitHub

Initialize Git.

```bash
git init
```

Add remote repository.

```bash
git remote add origin https://github.com/atulkamble/WebApp.git
```

Stage files.

```bash
git add .
```

Commit.

```bash
git commit -m "Initial Blazor App"
```

Push.

```bash
git branch -M main
```

```bash
git push -u origin main
```

---

# 🖥️ Step 7 - GitHub Desktop

Open

```
GitHub Desktop
```

Clone or open the repository.

Verify

```
Repository Name

WebApp
```

Check

```
Current Branch

main
```

Verify all project files are uploaded.

---

# ☁️ Step 8 - Create Azure App Service

Open

```
Azure Portal
```

Search

```
App Services
```

Click

```
Create
```

Select

```
Web App
```

---

## Configure Web App

| Setting          | Value                      |
| ---------------- | -------------------------- |
| Publish          | Code                       |
| Runtime Stack    | .NET 10 (Windows)          |
| Operating System | Windows                    |
| Region           | Canada Central             |
| Pricing Plan     | Free (F1) or Standard (S1) |
| App Name         | Unique Name                |

Click

```
Review + Create
```

Then

```
Create
```

Azure automatically provisions:

* Resource Group
* App Service Plan
* Web App

---

# ⚙️ Step 9 - Configure App Service

Open your Web App.

Navigate to

```
Settings

↓

Configuration

↓

General Settings
```

Verify

```
Stack

.NET 10
```

Operating System

```
Windows
```

Save changes if required.

---

# 🔄 Step 10 - Configure Continuous Deployment

Open

```
Deployment Center
```

Choose

```
Source

GitHub
```

Authorize GitHub.

Select

```
Organization
```

Select Repository

```
WebApp
```

Branch

```
main
```

Click

```
Save
```

Azure automatically creates a GitHub Actions workflow for continuous deployment. Every push to the configured branch triggers a new deployment.

---

# 📜 Step 11 - Monitor Deployment

Open

```
Deployment Center

↓

Logs
```

Verify

```
Build Started

↓

Build Successful

↓

Deployment Successful
```

You can also monitor workflow execution in

```
GitHub

↓

Actions
```

---

# 🌐 Step 12 - Access the Website

Copy the Web App URL.

Example

```
https://mywebappatulkamble-dbefdqbvdyadd7eb.canadacentral-01.azurewebsites.net/
```

Open it in your browser.

Expected Result

```
Blazor Web Application Running Successfully
```

---

# 📁 Project Structure

```
WebApp
│
├── Components
├── Pages
├── wwwroot
├── Program.cs
├── appsettings.json
├── WebApp.csproj
└── README.md
```

---

# 📦 Useful Commands

## Check Git

```bash
git status
```

```bash
git log
```

```bash
git pull
```

```bash
git push
```

---

## Azure CLI Login

```bash
az login
```

List subscriptions

```bash
az account list -o table
```

Current subscription

```bash
az account show
```

---

## .NET Commands

Restore

```bash
dotnet restore
```

Build

```bash
dotnet build
```

Run

```bash
dotnet run
```

Publish

```bash
dotnet publish
```

---

# 🚀 CI/CD Workflow

```text
Developer
      │
      ▼
Visual Studio
      │
      ▼
Git Commit
      │
      ▼
GitHub Repository
      │
      ▼
GitHub Actions
      │
      ▼
Azure Deployment Center
      │
      ▼
Azure App Service
      │
      ▼
Live Website
```

---

# 📚 Learning Outcomes

After completing this project, you will understand:

* Creating a Blazor Web Application
* Using Visual Studio for .NET development
* Managing source code with Git
* Hosting code on GitHub
* Creating Azure App Service
* Configuring Windows App Service
* Continuous Deployment with GitHub
* Monitoring deployment logs
* Accessing a live Azure-hosted website
* Basic CI/CD concepts using GitHub Actions and Azure App Service

---

# 🎯 Live Demo

```
https://mywebappatulkamble-dbefdqbvdyadd7eb.canadacentral-01.azurewebsites.net/
```

---

# 📖 References

* Microsoft Azure App Service Documentation
* ASP.NET Core Documentation
* GitHub Actions Documentation
* Azure CLI Documentation
