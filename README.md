# 🚀 The Essential DevOps Command Arsenal

Unlocking the power of modern infrastructure with the most critical commands for Linux, Docker, Kubernetes, Terraform, Ansible, and AWS CLI.

[![GitHub stars](https://img.shields.io/github/stars/alok-kumar8765/devops_commands?style=for-the-badge&color=FEDC56&logo=github)](https://github.com/alok-kumar8765/devops_commands/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/alok-kumar8765/devops_commands?style=for-the-badge&color=80A3D2&logo=github)](https://github.com/alok-kumar8765/devops_commands/network/members)
[![GitHub contributors](https://img.shields.io/github/contributors/alok-kumar8765/devops_commands?style=for-the-badge&color=25C370)](https://github.com/alok-kumar8765/devops_commands/graphs/contributors)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=for-the-badge)](https://github.com/alok-kumar8765/devops_commands/graphs/commit-activity)

---

## 📋 Table of Contents

1.  [Linux & System Basics](#1-linux--system-basics)
2.  [Git & Docker Containerization](#2-git--docker-containerization)
3.  [Kubernetes Orchestration](#3-kubernetes-orchestration)
4.  [Terraform Infrastructure as Code (IaC)](#4-terraform-infrastructure-as-code-iac)
5.  [Ansible Automation Engine](#5-ansible-automation-engine)
6.  [AWS Command Line Interface (CLI)](#6-aws-command-line-interface-cli)
7.  [Explore More: Video Resources](#7-explore-more-video-resources)

---

## 1. Linux & System Basics

The foundational commands for navigating the filesystem, managing files, and checking system health.

| Command | Description | Example |
| :--- | :--- | :--- |
| `ls -l` | List files and directories in long format (detailed info). | `ls -l /var/log` |
| `cd` | Change directory. | `cd /path/to/my/project` |
| `pwd` | Print Working Directory (shows current location). | `pwd` |
| `cp` | Copy files or directories. | `cp source.txt destination/` |
| `mv` | Move or rename files/directories. | `mv file.txt /new/location/` |
| `rm -rf` | **DANGEROUS:** Recursively and forcibly deletes files/folders. | `rm -rf old_folder/` |
| `cat` | Concatenate and display file content. | `cat config.yml` |
| `tail -f` | View the end of a file and follow new content (essential for logs). | `tail -f /var/log/syslog` |
| `grep` | Search text within files using patterns. | `cat server.log \| grep "ERROR"` |
| `chmod` | Change file permissions (Read, Write, Execute). | `chmod +x script.sh` |

### Detailed Explanation & Indentation

1.  **File Navigation and Management**
    * **`cd /path/to/dir`**: Changes the current directory to the specified path.
    * **`rm file.txt`**: Deletes a specific file. Use `rm -r` to delete a folder recursively.
2.  **Viewing File Content**
    * **`cat file.txt`**: Used to view the *entire* content of a file instantly.
    * **`tail -f logfile.log`**: Crucial for debugging. The `-f` (follow) flag keeps the output open and shows new lines as they are written to the log.

## 2. Git & Docker Containerization

Managing code version control (Git) and running isolated applications (Docker).

| Command | Tool | Description | Example |
| :--- | :--- | :--- | :--- |
| `docker version` | Docker | Shows information about the Docker client and server (daemon). | `docker version` |
| `docker ps` | Docker | Lists currently running containers. | `docker ps` |
| `docker ps -a` | Docker | Lists *all* containers, including stopped ones. | `docker ps -a` |
| `docker build` | Docker | Builds a Docker image from a Dockerfile. | `docker build -t myimage .` |
| `docker run` | Docker | Runs a command in a new container. | `docker run -d -p 8080:80 myimage` |
| `docker exec` | Docker | Execute a command inside a running container. | `docker exec -it container_id /bin/bash` |
| `git clone` | Git | Downloads a repository from a remote source. | `git clone [repo_url]` |
| `git commit` | Git | Records changes to the repository with a message. | `git commit -m "Feature: added auth"` |
| `docker logs` | Docker | Fetches the logs of a container. | `docker logs container_id` |

### Detailed Explanation & Indentation

1.  **Docker Lifecycle Commands**
    * **`docker build -t <tag_name> .`**: The `-t` tag names the image, and the `.` specifies that the Dockerfile is in the current directory.
    * **`docker run -d -p <host>:<container> <image>`**:
        * `-d`: Runs the container in **detached** mode (background).
        * `-p`: Maps a port from the host machine to the container.
    * **Cleanup Commands (By ID)**
        * `docker stop <id>`: Gracefully stops a running container.
        * `docker rm <id>`: Removes a stopped container.
        * `docker rmi <id>`: Removes a built image.
2.  **Essential Git Workflow**
    * `git add .`: Stages all changes for the next commit.
    * `git push origin <branch>`: Uploads local commit history to the remote repository.

## 3. Kubernetes Orchestration

Commands for managing containerized applications across a cluster of machines.

| Command | Description | Example |
| :--- | :--- | :--- |
| `kubectl cluster-info` | Display the addresses of the master and services. | `kubectl cluster-info` |
| `kubectl get nodes` | View cluster nodes and their status. | `kubectl get nodes` |
| `kubectl get pods` | View the status of application instances (Pods). | `kubectl get pods` |
| `kubectl get services` | View details about Services (how to access Pods). | `kubectl get services` |
| `kubectl apply -f` | Apply configuration changes from a YAML file. | `kubectl apply -f deployment.yaml` |
| `kubectl describe` | Show detailed state of a specific resource. | `kubectl describe pod my-app-1` |
| `kubectl logs` | Print the logs for a container in a pod. | `kubectl logs my-app-1 -c frontend` |
| `kubectl port-forward`| Forward one or more local ports to a pod. | `kubectl port-forward svc/my-service 8080:80` |

### Detailed Explanation & Indentation

1.  **Getting Resource Status (`get`)**
    * **`kubectl get`**: This is the most common command. It supports various resources like `pods`, `deployments`, `services`, `pvc`, and `namespaces`.
2.  **Debugging & Introspection**
    * **`kubectl describe <resource> <name>`**: Unlike `get`, which gives a summary, `describe` provides events, conditions, and full spec details, which is crucial for troubleshooting why a pod might be stuck.
3.  **Applying Configuration**
    * **`kubectl apply -f deployment.yaml`**: This command is idempotent, meaning you can run it multiple times, and it will only apply changes that are necessary (create, update, or delete resources as required).

## 4. Terraform Infrastructure as Code (IaC)

Managing cloud infrastructure lifecycle using configuration files.

| Command | Description | Example |
| :--- | :--- | :--- |
| `terraform init` | Initializes a working directory containing Terraform configuration files. | `terraform init` |
| `terraform validate` | Checks configuration files for syntactic and internal consistency. | `terraform validate` |
| `terraform fmt` | Rewrites configuration files to a canonical format and style. | `terraform fmt` |
| `terraform plan` | Generates an execution plan showing what actions will be taken. | `terraform plan -out tfplan` |
| `terraform apply` | Executes the actions proposed in a plan to provision infrastructure. | `terraform apply tfplan` |
| `terraform destroy` | Destroys all remote objects managed by the current configuration. | `terraform destroy` |
| `terraform output` | Extracts the values of output variables from the state file. | `terraform output web_endpoint` |
| `terraform workspace`| Manages separate named working environments. | `terraform workspace select staging` |

### Detailed Explanation & Indentation

1.  **The Core IaC Workflow**
    * **`init`**: Prepares the directory by downloading necessary **providers**. This is the first step in any new configuration.
    * **`plan`**: This is the **safety check**. It compares the desired state (in code) with the current state (remote infrastructure) and shows exactly what will be created, updated, or deleted.
    * **`apply`**: Confirms and executes the plan. **Never run `apply` without first reviewing the `plan` output.**
2.  **Advanced Commands**
    * **`terraform workspace`**: Essential for managing multiple environments (e.g., `dev`, `staging`, `prod`) with the same code. Each workspace maintains its own separate state file.

## 5. Ansible Automation Engine

Commands for IT automation, configuration management, and application deployment.

| Command | Description | Example |
| :--- | :--- | :--- |
| `ansible-playbook`| Runs the main automation script (the Playbook). | `ansible-playbook -i inventory.ini site.yml` |
| `ansible all -m ping`| Tests connectivity to all hosts defined in the inventory. | `ansible all -m ping -i inventory.ini` |
| `ansible all -a` | Executes a shell command on all remote hosts. | `ansible all -a "df -h" -i inventory.ini` |
| `ansible-vault` | Encrypts variables and files to secure sensitive data. | `ansible-vault encrypt vars/secret.yml` |
| `ansible -m setup` | Gathers system facts (OS, network, memory) from remote hosts. | `ansible webservers -m setup` |

### Detailed Explanation & Indentation

1.  **Ad-Hoc vs. Playbook**
    * **Ad-Hoc (`ansible ...`)**: Used for quick, one-off tasks (like checking uptime or pinging all hosts). It runs a single **module** (`-m`).
        * Example: `ansible all -a "launch shell command on remote host"`
    * **Playbook (`ansible-playbook`)**: Used for complex, multi-step, repeatable automation defined in a YAML file.
2.  **Security and State**
    * **`ansible-vault`**: Critical for any production environment. It encrypts passwords, API keys, and secrets that must be stored in the repository.

## 6. AWS Command Line Interface (CLI)

The official tool to manage AWS services from your terminal.

| Command | Service | Description | Example |
| :--- | :--- | :--- | :--- |
| `aws configure` | Global | Configures access key, secret key, region, and output format. | `aws configure` |
| `aws s3 ls` | S3 | Lists buckets or objects within a bucket. | `aws s3 ls s3://my-bucket-name` |
| `aws s3 cp` | S3 | Copies files/directories to or from S3. | `aws s3 cp local/file.txt s3://bucket/` |
| `aws ec2 describe-instances`| EC2 | Retrieves information about EC2 instances. | `aws ec2 describe-instances` |
| `aws iam create-user` | IAM | Creates a new IAM user. | `aws iam create-user --user-name alok-dev` |
| `aws sts get-caller-identity`| STS | Verifies the identity of the user/role being used. | `aws sts get-caller-identity` |

### Detailed Explanation & Indentation

1.  **Initial Setup**
    * **`aws configure`**: Interactive setup that saves credentials locally (`~/.aws/credentials`). **Never hardcode your credentials in configuration files.**
2.  **S3 Storage Operations**
    * **`aws s3 cp`**: This command is highly versatile and supports the `--recursive` flag to sync entire directories between your local machine and S3.
3.  **EC2 Management**
    * A common essential command for verification is **`aws ec2 describe-instances`** to quickly check running instances, states, and IPs.

## 7. Explore More: Video Resources

Dive deeper into these technologies with these essential video resources.

* **Linux/Shell:** [Video on Linux Basics for DevOps (YouTube)](https://www.youtube.com/results?search_query=linux+basics+for+devops)
* **Docker:** [Comprehensive Docker Tutorial (YouTube)](https://www.youtube.com/results?search_query=docker+tutorial+for+beginners)
* **Kubernetes:** [Kubernetes Full Course (YouTube)](https://www.youtube.com/results?search_query=kubernetes+full+course+for+beginners)
* **Terraform:** [HashiCorp Terraform IaC Tutorial (YouTube)](https://www.youtube.com/results?search_query=terraform+iac+tutorial)
* **Ansible:** [Ansible 101 for Configuration Management (YouTube)](https://www.youtube.com/results?search_query=ansible+101+tutorial)
* **AWS CLI:** [Mastering the AWS Command Line (YouTube)](https://www.youtube.com/results?search_query=mastering+aws+cli)

---

<img src="https://github.com/alok-kumar8765/devops_commands/blob/main/IMG_176.jpg" height="50%" width="50%">

*Created by [alok-kumar8765] - Licensed under MIT.*