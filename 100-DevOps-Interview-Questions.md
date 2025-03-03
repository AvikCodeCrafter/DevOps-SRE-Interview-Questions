# 100 DevOps Interview Questions and Answers

## 1. What is DevOps Lifecycle?

The DevOps lifecycle includes the following phases:

- **Plan**: Define project requirements and architecture.
- **Develop**: Write and test the code.
- **Build**: Convert source code into executable software.
- **Test**: Automated and manual testing.
- **Release**: Deploy the application to staging/production.
- **Deploy**: Deliver updates to users.
- **Operate**: Manage and monitor the application in production.
- **Monitor**: Use logging and monitoring tools to gather feedback.

---

## 2. Have you used any Linux Flavors, if yes, which one?

Some commonly used Linux distributions in DevOps are:

- **Ubuntu** (Popular for cloud and DevOps environments)
- **CentOS** (Stable for enterprise applications)
- **RedHat Enterprise Linux (RHEL)** (Enterprise-level Linux distribution)
- **Debian** (A stable choice for server environments)

---

## 3. What is the command to change the ownership and permission of a file or directory in Linux?

- **Change Ownership**: `chown user:group filename`
- **Change Permissions**: `chmod 755 filename`

Example:

```bash
chown ubuntu:ubuntu /var/www/html
chmod 644 index.html
```

---

## 4. How do you manage and view running processes in Linux?

- `ps aux` → View all running processes
- `top` or `htop` → Interactive process monitoring
- `kill <PID>` → Kill a specific process
- `killall <process_name>` → Kill all processes by name

---

## 5. What is SSH?

SSH (Secure Shell) is a protocol used for securely accessing remote machines over an encrypted connection.
Example:

```bash
ssh user@remote-server
```

---

## 6. What is DNS (Domain Name System), and how does it work?

DNS translates domain names (e.g., google.com) into IP addresses (e.g., 142.250.190.14). It follows a hierarchical structure:

- **Root DNS Servers**
- **TLD (Top-Level Domain) Servers**
- **Authoritative DNS Servers**

---

## 7. What is NAT (Network Address Translation), and why is it used?

NAT allows private IP addresses to communicate with the internet using a single public IP. It is used for:

- Conserving IPv4 addresses
- Providing security

---

## 8. Explain the difference between TCP and UDP Protocols?

| Feature     | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
| ----------- | ----------------------------------- | ---------------------------- |
| Connection  | Connection-oriented                 | Connectionless               |
| Reliability | Reliable                            | Unreliable                   |
| Speed       | Slower                              | Faster                       |
| Use Case    | Web browsing, file transfer         | Video streaming, gaming      |

---

## 9. What is Git, and how do we use it in DevOps?

Git is a version control system used to track changes in code.

Example:

```bash
git init  
git add .  
git commit -m "Initial Commit"  
git push origin main  
```

---

## 10. Explain the workflow of how to push the code from a local machine?

1. `git add .` → Add changes
2. `git commit -m "Message"` → Commit changes
3. `git push origin branch-name` → Push changes

---

## 11. How do you revert a commit that you made in your repository?

- `git revert <commit-hash>` → Creates a new commit that undoes changes
- `git reset --hard <commit-hash>` → Deletes commits

---

## 12. What is a Branch in a Repository?

A branch is an independent line of development in Git.
Example:

```bash
git branch feature-branch  
git checkout feature-branch  
```

---

## 13. What cloud platforms are you familiar with?

- AWS (Amazon Web Services)
- Microsoft Azure
- Google Cloud Platform (GCP)

---

## 14. What is VPC in cloud?

VPC (Virtual Private Cloud) is a logically isolated network in the cloud.

---

## 15. What is the difference between a Private and Public Subnet?

- **Public Subnet**: Has internet access via an internet gateway.
- **Private Subnet**: No direct internet access.

---

## 16. What is the difference between Reserved Instance and Spot Instances?

- **Reserved Instance**: Fixed-term pricing, cost-effective for predictable workloads.
- **Spot Instance**: On-demand, cheaper but can be terminated anytime.

---

## 17. What is AWS CloudFormation?

CloudFormation is an Infrastructure-as-Code (IaC) tool used to automate AWS infrastructure deployment.

---

## 18. What are the popular IaC tools have you used?

- Terraform
- AWS CloudFormation
- Ansible

---

## 19. What is the difference between Terraform & Ansible?

| Feature | Terraform              | Ansible                  |
| ------- | ---------------------- | ------------------------ |
| Type    | IaC Tool               | Configuration Management |
| Purpose | Creates infrastructure | Manages configuration    |

---

## 20. What is a Playbook in Ansible?

A playbook is a YAML file that contains automation scripts.

---

## 21. What is a State File in Terraform?

A file that keeps track of the infrastructure's current state.

---

## 22. What is Terraform Remote State Backend?

It stores Terraform state files remotely (e.g., S3 bucket, Consul, etc.).

---

## 23. What is the Difference between Virtualization and Containerization?

- **Virtualization** → Uses VMs, heavier.
- **Containerization** → Uses Docker, lightweight.

---

## 24. What problem does Docker solve?

- Eliminates dependency issues
- Enables lightweight, fast deployments

---

## 25. What is a Dockerfile and why do we use it?

A script defining how to build a Docker image.

Example:

```dockerfile
FROM ubuntu  
RUN apt-get update  
CMD ["echo", "Hello, Docker!"]  
```

---

## 26. Explain the workflow of how a Docker Container is created?
1. **Pull Image**: Download the required image from Docker Hub using `docker pull <image_name>`.
2. **Create & Start a Container**: Use `docker run -d <image_name>` to create and start a container.
3. **Container Execution**: The container runs the application inside the environment defined by the image.
4. **View Running Containers**: Check running containers with `docker ps`.
5. **Manage Containers**: Start, stop, restart, or remove containers using `docker start/stop/rm <container_id>`.
6. **Persistent Storage**: Use volumes (`-v /host/path:/container/path`) to persist data.
7. **Networking**: Expose ports (`-p 8080:80`) to allow external access.

---

## 27. How do you manage multiple Containers?
Multiple containers are managed using:
- **Docker Compose**: Define multi-container applications using a `docker-compose.yml` file.
- **Docker Swarm**: A native clustering tool for container orchestration.
- **Kubernetes**: A powerful container orchestration system.
- **Networking & Volume Management**: Use Docker networks (`docker network create my_network`) and volumes (`docker volume create my_volume`).
- **Resource Limits**: Control CPU & memory using `--memory` and `--cpus` flags.

---

## 28. What is CI and CD in CICD?
- **CI (Continuous Integration)**: Automates code merging, testing, and builds when developers push changes.
- **CD (Continuous Deployment/Delivery)**: Ensures that new code is automatically deployed to production (Deployment) or made available for manual release (Delivery).

---

## 29. What CICD tools have you used in the past?
- Jenkins
- GitHub Actions
- GitLab CI/CD
- CircleCI
- Travis CI
- AWS CodePipeline
- Azure DevOps

---

## 30. How will you create a CICD pipeline to update the website or app on every commit to a particular branch?
1. **Set up a Repository**: Use GitHub/GitLab/Bitbucket.
2. **Create a Jenkins Pipeline**:
   - Clone the repo on every push (`git checkout <branch>`).
   - Run unit tests (`mvn test`, `npm test`).
   - Build the application (`mvn package`, `docker build`).
   - Deploy the updated app to the server using `scp`, `kubectl apply`, or `ansible`.
   - Notify developers using Slack, email, or webhooks.

---

## 31. Explain staging, production, and testing environment.
- **Testing**: Internal environment for developers to test code.
- **Staging**: A pre-production environment to simulate real-world use cases.
- **Production**: The live environment accessed by end-users.

---

## 32. What is a Blue-Green Deployment?
A **Blue-Green Deployment** minimizes downtime by maintaining two environments:
- **Blue (Active)**: Running production version.
- **Green (New Release)**: New version deployed.
- Switch traffic to Green once tested.

---

## 33. Explain Canary Deployment?
A **Canary Deployment** gradually rolls out a new version to a small percentage of users before full release.
- If successful, expand rollout.
- If issues occur, rollback to stable release.

---

## 34. What is the biggest issue you faced, and how did you resolve it?
Example:
- **Issue**: Application downtime due to database migration failure.
- **Solution**:  
  - Implemented database versioning (Flyway, Liquibase).
  - Used Blue-Green deployment to test changes.
  - Created automated rollback scripts.

---

## 35. How do you scale your application?
- **Horizontal Scaling**: Add more instances (`docker-compose scale`, Kubernetes replicas).
- **Vertical Scaling**: Increase CPU/RAM allocation.
- **Load Balancing**: Use Nginx, HAProxy, AWS ALB.
- **Auto-scaling**: AWS Auto Scaling, Kubernetes HPA.

---

## 36. How do you rollback if something fails?
- **Git Revert**: Revert to the previous commit.
- **Docker Rollback**: Use `docker service update --rollback`.
- **Kubernetes Rollback**: `kubectl rollout undo deployment`.
- **Jenkins Rollback**: Restore artifacts from backup.

---

## 37. How do you automate deployments?
Using CI/CD pipelines with tools like:
- **Jenkins, GitHub Actions, GitLab CI/CD**
- **Ansible, Terraform** for Infrastructure as Code
- **Docker & Kubernetes** for containerized apps

---

## 38. Which tools have you used for automating deployments?
- **CI/CD**: Jenkins, GitHub Actions, GitLab CI
- **Configuration Management**: Ansible, Puppet
- **Container Orchestration**: Kubernetes, Docker Swarm
- **Infrastructure as Code**: Terraform, CloudFormation

---

## 39. Have you written any Jenkins Pipeline from scratch?
Yes, using **Declarative** and **Scripted Pipelines**. Example:
```groovy
pipeline {
    agent any
    stages {
        stage('Build') { steps { sh 'mvn package' } }
        stage('Test') { steps { sh 'mvn test' } }
        stage('Deploy') { steps { sh 'scp target/app.war user@server:/deploy/' } }
    }
}
```

---

## 40. Mention some plugins you have used in Jenkins?
- Git Plugin
- Pipeline Plugin
- Kubernetes Plugin
- Docker Plugin
- Slack Notification Plugin
- SonarQube Plugin

---

## 41. What is CI/CD?
CI/CD automates software integration, testing, and deployment.
- **CI**: Frequent code commits with automated testing.
- **CD**: Automated or manual deployment to production.

---

## 42. How can you create backup and copy files in Jenkins?
- Backup using `cp -r $JENKINS_HOME /backup/jenkins/`.
- Use Jenkins ThinBackup plugin.

---

## 43. Assume you have 2 Jenkins jobs. The first job completed successfully, but the 2nd job failed. What will you do?
- **Check logs** for error details.
- **Re-run the job** after fixing issues.
- **Trigger rollback** if needed.

---

## 44. Process to integrate Git with Jenkins?
1. Install Git Plugin in Jenkins.
2. Configure GitHub credentials.
3. Use Git repository URL in Jenkins job configuration.

---

## 45. What is DSL in Jenkins?
**DSL (Domain Specific Language)** in Jenkins (Job DSL Plugin) allows creating Jenkins jobs programmatically using Groovy scripts.

---

## 46. Why use Jenkins instead of Bamboo?
- Jenkins is **open-source**, Bamboo is **paid**.
- Jenkins has a **larger plugin ecosystem**.
- Bamboo has **better Bitbucket integration**.

---

## 47. How to deploy a custom build of a code plugin to Jenkins?
- Place the `.hpi` or `.jpi` file in `$JENKINS_HOME/plugins`.
- Restart Jenkins.

---

## 48. What is the use of Jenkins home directory?
- Stores job configurations, logs, plugins, and user data.
- Default location: `/var/lib/jenkins/`.

---

## 49. How do you take a backup of Jenkins Jobs?
- Copy `JENKINS_HOME/jobs/`.
- Use **ThinBackup plugin**.

---

## 50. How to configure Jenkins nodes/agents with Jenkins master?
- Add a new node in **Manage Jenkins > Nodes**.
- Launch agent via SSH or JNLP.

---

## 51. What’s the difference between Recreate and Rolling Update strategies?
**Recreate Strategy:**
- Terminates all existing pods before creating new ones.
- Causes downtime as all old pods are deleted simultaneously.
- Used when new deployments require a complete restart.

**Rolling Update Strategy:**
- Gradually replaces old pods with new ones to ensure zero downtime.
- Uses `maxUnavailable` and `maxSurge` parameters to control rollout.
- Preferred for production environments where uptime is critical.

## 52. Why is Kubernetes widely used in modern organizations?
- Automates container deployment, scaling, and operations.
- Provides high availability and fault tolerance.
- Works well with microservices architectures.
- Enables multi-cloud and hybrid cloud environments.
- Supports declarative infrastructure via YAML manifests.

## 53. What are Cluster IP, Headless Services, and when should you use them?
**Cluster IP:**
- Default service type.
- Exposes the service within the Kubernetes cluster.
- Used for internal communication between pods.

**Headless Service:**
- Defined with `clusterIP: None`.
- Does not allocate a virtual IP.
- Used when clients need direct access to individual pod IPs (e.g., StatefulSets, databases).

## 54. What are stateless and stateful in YAML files?
**Stateless Applications:**
- Do not persist data between sessions.
- Can be freely restarted and scaled.
- Example: Web servers, API services.

**Stateful Applications:**
- Maintain state across restarts.
- Require persistent storage (e.g., databases, messaging queues).
- Deployed using StatefulSets in Kubernetes.

## 55. What are the different Kubernetes services, and how do they work?
- **ClusterIP:** Internal access only.
- **NodePort:** Exposes service on a static port on each node.
- **LoadBalancer:** Uses a cloud provider's load balancer to expose services externally.
- **Headless Service:** No ClusterIP, directly resolves to pod IPs.

## 56. What is a Terraform state file, and why is it important?
- Stores the current state of infrastructure.
- Tracks resources managed by Terraform.
- Helps in detecting changes and preventing configuration drift.

## 57. What resources have you created using Terraform?
- AWS EC2 instances, VPCs, subnets, security groups.
- RDS instances, S3 buckets, IAM roles.
- Kubernetes clusters (EKS, GKE, AKS).
- Load balancers, Route 53 DNS records.

## 58. If an RDS instance is created via Terraform but later modified manually, how do you reconcile the changes?
- Run `terraform plan` to detect drift.
- Use `terraform apply` to override manual changes.
- If needed, import the changes using `terraform import`.

## 59. What is a Terraform local name, and how is it used?
- Defined using `locals` block in Terraform.
- Used to store reusable expressions.
- Example:
  ```hcl
  locals {
    env = "dev"
  }
  output "environment" {
    value = local.env
  }
  ```

## 60. What are Docker Volumes, and why use them instead of EC2 storage?
- Persist data across container restarts.
- Decoupled from the container lifecycle.
- Can be shared among multiple containers.
- More flexible than EC2 instance storage.

## 61. Is Docker volume data persistent?
- Yes, data in Docker volumes persists even if containers are stopped or removed.

## 62. How do you implement a CI/CD pipeline? Can you write a Jenkins pipeline?
- Steps:
  1. Code is pushed to GitHub.
  2. Jenkins detects changes and triggers a build.
  3. Builds artifacts and runs tests.
  4. Deploys to a Kubernetes cluster.

- **Jenkinsfile Example:**
  ```groovy
  pipeline {
    agent any
    stages {
      stage('Build') {
        steps {
          sh 'mvn clean package'
        }
      }
      stage('Test') {
        steps {
          sh 'mvn test'
        }
      }
      stage('Deploy') {
        steps {
          sh 'kubectl apply -f deployment.yaml'
        }
      }
    }
  }
  ```

## 63. Why use ArgoCD for Kubernetes deployments? How does it work end to end?
- **Why ArgoCD?**
  - GitOps approach for Kubernetes deployments.
  - Ensures cluster state matches Git repository.
  - Provides a UI and audit trail for deployments.

- **How it works:**
  1. Define Kubernetes manifests in a Git repository.
  2. ArgoCD continuously monitors the repo.
  3. If drift is detected, ArgoCD syncs changes.
  4. Ensures Kubernetes deployments are always in the desired state.

## 64. How do you establish communication between frontend and backend services?
- Use Kubernetes services (ClusterIP, LoadBalancer, Ingress).
- Example: Backend as a service exposed via ClusterIP.
- Frontend connects via service name (`http://backend-service:8080`).

## 65. What are the key services used in your project?
- Kubernetes (EKS/GKE/AKS), ArgoCD, Prometheus, Grafana.
- Terraform for infrastructure as code.
- CI/CD tools like Jenkins/GitHub Actions.
- Database services (RDS, PostgreSQL, MongoDB).

## 66. When do you use headless services vs. cluster services?
- **Headless Services:** When direct pod-to-pod communication is needed (e.g., databases, stateful applications).
- **ClusterIP Services:** When internal service discovery is sufficient.

## 67. What’s the best way to deploy and manage microservices in a Kubernetes environment?
- Use **Helm charts** for packaging microservices.
- Implement **ArgoCD/GitOps** for deployment automation.
- Set up **Horizontal Pod Autoscaler** for scalability.
- Use **service mesh (Istio/Linkerd)** for networking.
- Implement **monitoring (Prometheus/Grafana)**.

## 68. How does your organization handle cloud-native deployments efficiently?
- Uses **Infrastructure as Code (Terraform, Helm)**.
- Implements **CI/CD pipelines (Jenkins, GitHub Actions, ArgoCD)**.
- Adopts **observability tools (Prometheus, Loki, ELK)**.
- Implements **auto-scaling and cost optimization strategies**.



