# BasicStockApp - Docker Setup and Running Guide

This document provides a step-by-step guide to run the **BasicStockApp API** in a Docker environment. Follow the instructions below to quickly and securely set up the application.

---

## View Turkish Version

For the Turkish version of this guide, please see: [README-TR.md](readme-tr.md)

---

## Prerequisites

* **Docker** and **Docker Compose** must be installed on your system.

  * [Docker Desktop](https://www.docker.com/products/docker-desktop/) (for Windows/macOS) or the appropriate Docker installation for your Linux distribution is required.
* Internet connection is required.
* Git command must be available on your system.

---

## Step 1: Install Docker and Docker Compose

1. Download and install Docker Desktop from the [official website](https://www.docker.com/products/docker-desktop/).
2. After installation, open a terminal or PowerShell and verify the installation with the following commands:

```bash
docker --version
docker-compose --version
```

> If version information appears, Docker has been successfully installed.

---

## Step 2: Pull BasicStockApp API Docker Image

1. Open a terminal or PowerShell.
2. Pull the API image from the official Docker Hub repository:

```bash
docker pull yeteam/basicstockapp-api-ssl
```

3. After the pull is complete, check your images with:

```bash
docker images
```

---

## Step 3: Clone the Project from Git

1. Navigate to your desired directory. For example:

```bash
cd C:\Users\<YourUsername>\Desktop
```

2. Clone the repository:

```bash
git clone https://github.com/Y-E-Projects/BasicStockApp-Api-Docker-MySQL.git
```

3. Navigate to the cloned directory:

```bash
cd BasicStockApp-Api-Docker-MySQL
```

---

## Step 4: Start the Application with Docker Compose

1. In the directory containing the Docker Compose file, run:

```bash
docker-compose up -d
```

2. Once the command executes, containers will start in the background. Check the status with:

```bash
docker ps
```

* You should see `mymarket-mysql` and `basicstockapp-api` containers running.

3. The application is now running at:

* SSL: [**https://localhost:5001**](https://localhost:5001)

---

## Step 5: Restarting or Stopping the Application

* **To stop:**

```bash
docker-compose down
```

* **To restart:**
  You can use Docker Desktop, go to `Containers / Apps`, select the relevant container, and click **Start**, or in terminal:

```bash
docker-compose up -d
```

---

## Summary

This guide covers:

* Installing and verifying Docker,
* Pulling the API image (standard or SSL),
* Cloning the Git repository,
* Starting and stopping containers using Docker Compose,

allowing you to run **BasicStockApp API** on your local environment.
