# Lab 09a – Implement Web Apps

## Lab Introduction
In this lab, you explore Azure Web Apps using Azure App Service. You deploy a PHP-based web application from an external GitHub repository, configure deployment slots, perform a slot swap, and enable autoscaling to handle changes in demand.

**Estimated time:** 20 minutes  
**Region:** East US (or nearest available)

---

## Lab Scenario
Your organization is planning to migrate company websites from on-premises Windows servers to Azure. The websites run on PHP and the existing hardware is nearing end-of-life. Azure App Service is evaluated as a Platform-as-a-Service (PaaS) solution to reduce infrastructure management and hardware costs.

---

## Job Skills
- Create and configure Azure Web Apps
- Configure deployment slots
- Enable continuous deployment from GitHub
- Swap deployment slots
- Configure and test autoscaling for web applications

---

## Task 1: Create and Configure an Azure Web App

An Azure Web App was created using Azure App Service to host a PHP application.

### Configuration Summary

- Resource group: az104-rg9
- Web app name: *globally unique*
- Publish: Code
- Runtime stack: PHP 8.2
- Operating system: Linux
- Region: East US
- App Service plan: Premium V3 (P1V3)
- Zone redundancy: Default

> Azure App Service abstracts server management and provides built-in scalability, security, and monitoring.

After deployment, the default App Service page was verified using the provided default domain URL.

---

## Task 2: Create and Configure a Deployment Slot

A deployment slot was created to support testing before pushing changes to production.

### Deployment Slot Details

- Slot name: staging
- Clone settings: No

Both **Production** and **Staging** slots are now available.  
The staging slot has a unique URL separate from production.

> Deployment slots allow safe testing and validation before exposing changes to end users.

---

## Task 3: Configure Web App Deployment Settings

Continuous deployment was configured for the **staging** slot using an external GitHub repository.

### Deployment Configuration

- Source: External Git
- Repository: `https://github.com/Azure-Samples/php-docs-hello-world`

- Branch: master

After saving the settings, the staging slot was accessed via its default domain URL and verified to display: `Hello World`


> Deployment may take a few minutes. Refresh the browser if needed.

---

## Task 4: Swap Deployment Slots

The staging slot was swapped with the production slot to promote the tested version of the application.

### Slot Swap Summary

- Source slot: staging
- Target slot: production

After the swap completed:
- The production URL now displays the **Hello World** application
- No downtime occurred during the swap

> Slot swapping is a best practice for zero-downtime deployments.

---

## Task 5: Configure and Test Autoscaling

Autoscaling was configured to handle increases in web traffic.

### Autoscale Configuration

- Scaling mode: Automatic
- Maximum burst instances: 2

Autoscaling ensures the application maintains performance during traffic spikes while controlling costs during low usage.

---

## Load Testing the Web App

A load test was created to validate autoscaling behavior.

### Load Test Steps

- Load test created using Azure Load Testing
- HTTP request configured using the production web app URL
- Live metrics observed:
  - Virtual users
  - Response time
  - Requests per second

The test was manually stopped after reviewing live performance metrics.

---

## Key Takeaways:
- Azure App Service provides a fully managed platform for web applications
- Web Apps support multiple runtime stacks including PHP, Java, .NET, and Python
- Deployment slots enable safe testing and zero-downtime releases
- Autoscaling helps maintain performance during traffic spikes
- Azure provides built-in diagnostics and load testing tools


