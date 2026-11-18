# Kostal Project: Integration & Documentation

This documentation describes the step-by-step approach, architecture, and implementation of the Kostal project.cyxcyc

## 📋 Overview & Objectives
The goal of this project was to connect, collect data from, and structurally analyze Kostal inverter and energy management data in order to monitor energy flows and performance metrics transparently dfgdfg

---

## 🚀 Step-by-Step Documentation

### 1. Requirements Analysis & Interface Clarification
* **Data Source Identification:** Determining available endpoints, protocols, and data structures (e.g., Modbus TCP, REST API, or the Kostal device's local web server).
* **Target Metrics Definition:** Establishing which values (current PV generation, household consumption, feed-in, battery state of charge, etc.) need to be polled regularly.

### 2. API Exploration & Testing with Postman
* **Request Setup:** Creating a Postman collection for targeted interaction with the Kostal inverter's REST endpoints.
* **Validation & Auth:** Testing authentication mechanisms (if applicable) and checking JSON payloads and response times.
* **Mocking & Documentation:** Documenting response structures for subsequent implementation in the automation pipeline.

![Postman Logo](./assets/postman.png)

### 3. Architecture Design & Data Pipeline
* **Automation Layer:** Setting up workflows (e.g., using n8n) utilizing the endpoints validated in Postman for automated polling at defined intervals.
* **Database Design:** Setting up a structured relational database (PostgreSQL) for persistent storage of historical measurements and time series.
* **Interface Design:** Defining fault tolerances, retry mechanisms for connection drops, and logging.

![n8n Workflow](./assets/n8n.png)

### 4. Implementation & Automation
* **API/Protocol Integration:** Building HTTP/Modbus queries within the automation environment and validating raw responses.
* **Data Cleaning & Transformation:** Mapping raw data to a clean schema (timestamp, metric, unit, status).
* **Automated Storage:** Writing the transformed datasets into the PostgreSQL database.

![PostgreSQL Logo](./assets/Postgres.png)

### 5. Visualization & Monitoring
* **BI Tool Integration:** Connecting the database to Power BI to create dashboards.
* **Dashboard Design:** Visualizing key performance indicators such as self-sufficiency rate, daily solar yield, grid import, and self-consumption over time.

![PowerBI Logo](./assets/PowerBI.png)

---

## 🛠️ Tech Stack
* **API Testing & Documentation:** Postman
* **Automation:** n8n (Docker-based)
* **Database:** PostgreSQL
* **Visualization:** Power BI
* **Protocols / Interfaces:** REST API / Modbus TCP


