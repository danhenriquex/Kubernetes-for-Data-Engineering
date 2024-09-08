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
│   ├── hello.py	           # Example DAG definition
│   ├── fetch_and_preview.py       # Example DAG definition
├── k8s                            # Contains the configuration for deploying Airflow using Helm
│   ├── dashboard-adminuser.yaml	           # 
│   ├── dashboard-clusterrole.yaml       
│   ├── dashboard-secret.yaml 
├── README.md                      
└── .gitignore                     # Files ignored by Git

```
</div>

### Scripts Overview

- `dashboard-adminuser.yaml`: This file creates a ServiceAccount called admin-user in the kubernetes-dashboard namespace. Service accounts are used to provide an identity for processes that run inside pods, and here it's specifically for admin-level access to the Kubernetes dashboard.
- `dashboard-clusterrole.yaml`: This file creates a ClusterRoleBinding, which binds the admin-user ServiceAccount to the cluster-admin role. The cluster-admin role grants the highest level of access to the Kubernetes cluster, allowing full control over all resources.
- `dashboard-secret.yaml`: This file generates a Secret containing the token for the admin-user ServiceAccount. This token is used to authenticate and access the Kubernetes Dashboard with admin privileges.
- `fetch_and_preview.py`: Automates the process of fetching sales data from a URL, processing it using Pandas, and then previewing the results.
- `hello.py`: Defines a simple Airflow DAG that schedules two tasks. These tasks use BashOperator to execute bash commands, demonstrating a basic workflow where one task prints "Hello World" and the other prints "Hello Data Mastery Lab".

### Getting Started

To get started with this project, follow these steps:

1. **Clone the Repository:**

   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```
   
2. **User Configurations:**

   ```bash
   # Create the ServiceAccount.
   kubectl apply -f dashboard-adminuser.yaml
   #  bind the admin-user to the cluster-admin role
   kubectl apply -f dashboard-clusterrole.yaml
   # Generate the token
   kubectl apply -f dashboard-secret.yaml
   ```
3. **Installing Kubernetes Dashboard:**
   
   ```bash
   # Deploys the Kubernetes Dashboard to the cluster.
   kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

   # Starts a proxy server that allows you to access the Kubernetes Dashboard locally
   kubectl proxy

   # Retrieves the authentication token required to log in to the Kubernetes Dashboard with the admin-user account.
   kubectl get secret admin-user -n kubernetes-dashboard -o jsonpath={".data.token"} | base64 -d
   ```

4. **Configuring Airflow:**

   ```bash
   
   helm repo add apache-airflow https://airflow.apache.org\n
   
   helm repo update
   
   helm install airflow apache-airflow/airflow --namespace airflow --create-namespace --debug
   
   kubectl port-forward svc/airflow-webserver 8080:8080 --namespace airflow
   ```
   

### What I learned
	
- Kubernetes: Mastered deployment and orchestration of containerized applications using Kubernetes.
- Airflow: Developed an understanding of workflow orchestration and scheduling using Apache Airflow.
- Helm: Gained experience in managing Kubernetes packages and simplifying complex deployments..
- Docker: Improved my ability to create consistent environments for development, testing, and production.
- Python: Enhanced my skills in Python for data pipeline automation and management.

