<h1 align="center">🚗 Data Engineering Project</h1>
<p align="center" id="objetivo">Learning Data Engineering. 
</p> 

<p align="center">
 <a href="#overview">Overview</a> •
 <a href="#features">Technologies and Tools Used</a> •
 <a href="#roadmap">Project Structure</a> • 
 <a href="#tecnologias">Getting Started</a> • 
 <a href="#learned">What I Learned</a> •
 <a href="#author">Author</a>
</p>

<h4 align="center"> 
	🚧  Data Engineering Project 🚀 Finished  🚧 
</h4>

<div align="center">
	<a href="https://wakatime.com/badge/user/8028aaab-232d-4832-8b66-f103e1d713b9/project/19e4d374-1f72-4f92-8ff9-385577530404"><img src="https://wakatime.com/badge/user/8028aaab-232d-4832-8b66-f103e1d713b9/project/19e4d374-1f72-4f92-8ff9-385577530404.svg" alt="wakatime"></a>
</div>

### Overview

<div style='margin: 20px' id="overview">
This project demonstrates how Kubernetes and Apache Airflow were used to manage **DAGs** (Directed Acyclic Graphs) for data pipelines in an automated and scalable environment. The primary goal of this project is to implement robust orchestration for data engineering tasks, providing easy scheduling, monitoring, and error handling.
</div>

### Technologies and Tools Used

<div id="features">

- **Kubernetes**: A system for automating deployment, scaling, and management of containerized applications.
- **Apache Airflow**: Used to manage and orchestrate workflows through DAGs, making it easier to monitor and schedule pipelines.
- **Python**: The primary language used for scripting the data pipelines and interactions with Airflow.
- **Docker**: Ensures consistent deployment environments and allows seamless development across machines.
- **Helm**: Used for managing Kubernetes packages, simplifying the deployment of Airflow.

</div>

<div id="roadmap">

### Project Structure

```bash
├── dags/                          # Contains the DAGs for the Airflow scheduler
│   ├── example_dag.py             # Example DAG definition
├── values.yaml                    # Configuration for deploying Airflow using Helm
├── README.md                      # This file
└── .gitignore                     # Files ignored by Git
