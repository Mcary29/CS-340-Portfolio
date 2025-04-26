# Grazioso Salvare Rescue Dashboard

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tools and Technologies](#tools-and-technologies)
- [Setup and Installation](#setup-and-installation)
- [Software Architecture](#software-architecture)
- [Challenges and Solutions](#challenges-and-solutions)
- [Reflection](#reflection)

---

## Project Overview
This project presents an interactive dashboard application designed for **Grazioso Salvare**, a company specializing in the rescue and training of animals for service purposes. The dashboard filters and visualizes animal shelter data from the Austin Animal Center to help rescue coordinators identify suitable animals for various operations.

The dashboard enables dynamic filtering by rescue type, displays breed distributions through interactive charts, and visualizes animal geolocations on a map — all updated in real-time based on user inputs.

---

## Features
- **Filter animals** based on operation type:
  - Water Rescue
  - Mountain/Wilderness Rescue
  - Disaster/Individual Tracking
- **View breed distribution** with dynamic pie charts
- **Visualize animal geolocations** on an interactive map
- **Interactive data table** for browsing animal details
- **Real-time dashboard updates** via user selection
- **Clean modular code** leveraging CRUD operations for database interaction

---

## Tools and Technologies
- **MongoDB**: NoSQL database for flexible, schema-less data storage
- **Python**: Core application logic
- **Dash (Plotly)**: Web framework for building analytical web applications
- **JupyterDash**: Rendering the dashboard in Jupyter environments
- **Pandas**: Data manipulation and transformation
- **Dash Leaflet**: Geolocation map visualizations

---

## Setup and Installation

Follow these steps to reproduce the project environment:

### 1. Install Required Software
- Install [Python 3.10+](https://www.python.org/)
- Install [MongoDB Community Server](https://www.mongodb.com/try/download/community)

### 2. Install Required Python Libraries
Open a terminal and run:

```bash
pip install dash dash-bootstrap-components pandas pymongo plotly dash-leaflet
```

### 3. Load Data into MongoDB
- Start the MongoDB server on your machine.
- Load the Austin Animal Center data into a MongoDB database named `animals`.
  - You can use `mongoimport` or manually insert documents.

Example mongoimport command:
```bash
mongoimport --db animals --collection animals --file austin_animal_center.json --jsonArray
```

### 4. Run the Application
- Open the project directory.
- Launch the dashboard:
  - If running from a script:  
    ```bash
    python app.py
    ```
  - If using Jupyter Notebook:  
    Open the notebook and run all cells to start the dashboard.

- Open your web browser and navigate to the address provided (e.g., `http://127.0.0.1:8050/`).

---

## Software Architecture

This project was developed using a **Model-View-Controller (MVC)** design pattern:

- **Model**:  
  MongoDB database and a custom Python CRUD module to perform Create, Read, Update, Delete operations.
  
- **View**:  
  Dash components (graphs, maps, tables) that users interact with.

- **Controller**:  
  Dash callbacks connect user inputs to database queries and visualization updates.

Additionally, the dashboard design concept adheres to **RESTful principles** by treating server interactions (via PyMongo) like lightweight resource manipulations — enhancing modularity and scalability.

---

## Challenges and Solutions

| Challenge | Solution |
|:---------|:---------|
| **MongoDB ObjectId Formatting** | Removed the `_id` field before displaying documents in the Dash DataTable to avoid formatting issues. |
| **Dynamic Synchronization** | Crafted interconnected Dash callbacks so that filtering updates all widgets (charts, maps, tables) in real-time. |
| **Initial Callback Testing** | Used logging inside callback functions to debug and verify data flow between components. |

---

## Reflection

### Writing Maintainable, Readable, Adaptable Code
Modular design was key. The CRUD module created for Project One made Project Two much easier, allowing database operations to be reused and easily extended. This approach minimized code repetition and made troubleshooting more efficient.

### Problem-Solving as a Computer Scientist
I approached the project by carefully planning the database schema first, ensuring that the CRUD functions would support all expected dashboard queries. Compared to earlier assignments, this project required a stronger focus on real-time user interaction and scalable backend integration, encouraging a structured and iterative development strategy.

### Why Computer Science Matters
Computer scientists build innovative systems that solve real-world problems. This dashboard empowers Grazioso Salvare to make data-driven decisions, optimize resource allocation, and ultimately save more animals — showcasing how software solutions can have meaningful, tangible impacts.

---
