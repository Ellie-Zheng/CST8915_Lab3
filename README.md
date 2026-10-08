# CST8915 Lab 3 - CST8915 Full-stack Cloud-native Development: Deploying the Algonquin Pet Store on Azure

- **Student Name**: Ellie Zheng
- **Student ID**: 041078727
- **Course**: CST8915 Full-stack Cloud-native Development
- **Semester**: Fall 2026

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/qOCt-So0XVk)

---

## Links to the Three Service Repositories

- [`order-service`](https://github.com/Ellie-Zheng/cst8915-lab2-order-service)
- [`product-service`](https://github.com/Ellie-Zheng/cst8915-lab2-product-service)
- [`store-front`](https://github.com/Ellie-Zheng/cst8915-lab2-store-front)

---

## Reflection Questions

### What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?

Due to region restrictions on my Azure for Students subscription, I deployed the Store Front on an Azure VM instead of an Azure Static Web App, as advised by the instructor. Consequently, rather than passing environment variables during the GitHub Actions build/deployment pipeline, I managed the Product and Order Service URLs directly via a local `.env` file on the Store Front VM. The primary challenge was ensuring secure credential handling and consistent environment configurations across different deployment targets while keeping sensitive files out of version control(Git).

### How does deploying microservices on Azure Web App Service differ from running them locally?

Locally, services run on a single machine (my own laptop) and communicate seamlessly via `localhost` without complex network configurations. In Azure, microservices are decoupled across managed Web Apps (Product and Order services) and VMs (Store Front and RabbitMQ). This requires managing public HTTPS endpoints, enforcing secure inter-service communication, and configuring network access rules (such as inbound port rules for the RabbitMQ VM) to allow external service interaction.

### Why is it important to use environment variables for configurations in a cloud environment?

Environment variables let me change settings, such as service URLs and the RabbitMQ connection string, without changing the source code for each deployment. They also help keep credentials out of the GitHub repositories. In this lab, I configured the Order Service’s RabbitMQ connection string in Azure Web App settings and the Store Front's API URLs on its VM.
