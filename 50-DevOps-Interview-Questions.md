# 50 DevOps Interview Questions and Answers

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

1. Write a Dockerfile
2. Build image: `docker build -t myapp .`
3. Run container: `docker run myapp`

---

*(More questions and answers can be added as needed.)*

please 
