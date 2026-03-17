# snowmelt-floods
GIS analysis project to assess flood risk due to snow thawing in the springtime.

## 1. Project Prerequisites
[ ] Docker Desktop: Installed and running.

[ ] VS Code Extensions:

[ ] Dev Containers (by Microsoft)
<!-- 
[ ] Python & Jupyter

[ ] Git Bash: Used for terminal commands on Windows.
 -->
## 2. Core Project Files
Ensure your root directory contains these three files:

- `Dockerfile`: Defines the Linux environment and installs libgdal-dev.

- `requirements.txt`: Includes geopandas>=1.1.0.

- `docker-compose.yml`: Orchestrates the notebook and PostGIS database services.

## 3. Initialization Steps (The "First Time" Setup)
Run these commands in Git Bash from your project root:

Build and start the services:

```Bash
docker compose up -d
```

Verify container status:

Open Docker Desktop and ensure the *flood_lab* container is green.

## 4. Connecting VS Code to Docker
To get imports working in your IDE without local installation errors:

### 4.1. Attach to Container:

Press `Ctrl + Shift + P` -> *Dev Containers: Attach to Running Container*.

Select *flood_lab*.

### 4.2. Open the Project Folder:

Inside the new VS Code window, go to File > Open Folder...

Type /app and hit Enter.

### 4.3. Select the Kernel:

Open your .ipynb file.

Click Select Kernel (top right) and choose the Python 3.11 (Global) kernel inside the container.

## 5. Standard Operation (Daily Workflow)
Once the setup is done, your daily routine is:

### 5.1 `docker compose up -d` in Git Bash.

### 5.2 Attach via VS Code.

### 5.3 Shut down when finished: `docker compose down`

## 6. Troubleshooting Notes

Git Bash Pathing: If mounting volumes manually, use `//$(pwd)` to ensure Windows paths are translated correctly.

`ModuleNotFoundError`: This almost always means the notebook is using the local Windows Python kernel instead of the Docker Python kernel. Always check the top-right kernel label in VS Code.