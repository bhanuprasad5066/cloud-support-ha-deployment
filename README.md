
# High-Availability Multi-Tier Cloud Deployment with Monitoring & RCA-Based Incident Resolution

This project demonstrates the deployment of a highly available multi-tier web application using AWS EC2 and an Application Load Balancer, with monitoring, incident simulation, troubleshooting, and RCA documentation similar to real Cloud Support Engineer responsibilities.

---

## 🚀 Project Overview

The objective of this project is to:
- Deploy two EC2 instances running a web server
- Configure an Application Load Balancer to distribute traffic and ensure high availability
- Implement CloudWatch monitoring and alerts to detect performance issues
- Simulate cloud support incidents and perform troubleshooting
- Document issues using a ServiceNow-style RCA format

---

## 🧱 Architecture Components

| Component | Purpose |
|----------|---------|
| EC2 Instances (2) | Web servers hosting the application |
| Application Load Balancer | Distributes traffic & performs health checks |
| IAM Role | Monitoring access permissions |
| CloudWatch | Metrics, alarms, and monitoring |
| Security Groups | Controls inbound/outbound access |

```

User → Application Load Balancer → EC2 WebServer1
↳ EC2 WebServer2


## 🔧 Setup Steps

### 1️⃣ Launch EC2 Instances
- Launch 2 EC2 instances (Ubuntu / Amazon Linux)
- Install Apache web server:
```

sudo apt update
sudo apt install apache2 -y

```
- Modify index.html to identify the server:
```

echo "Hello from WebServer1" | sudo tee /var/www/html/index.html

```

### 2️⃣ Configure Application Load Balancer
- Create Application Load Balancer
- Add both instances to Target Group
- Enable health checks

### 3️⃣ IAM Role for Monitoring
- Attach CloudWatchAgentServerPolicy to the instance role

### 4️⃣ Monitoring & Alerts
- Enable CPU, memory, and disk metrics
- Create CloudWatch alarm:
```

Condition: CPUUtilization > 80% for 5 minutes
Action: Send notification

```

---

## 🔍 Incident Simulation & Troubleshooting

| Incident | Symptoms | Cause | Fix |
|----------|----------|-------|-----|
| Website unreachable | Page not loading | Apache stopped | `sudo systemctl restart apache2` |
| High CPU usage | Alert triggered | Stress process running | Kill process / restart service |
| SSH access denied | Cannot SSH | Security Group blocked port 22 | Allow port 22 in SG |
| Access denied to services | Permission error | IAM policy mismatch | Update IAM user permissions |

---

## 📝 RCA Documentation Sample

```

Incident ID: INC-001
Issue: Website inaccessible through Load Balancer

Root Cause:
Apache service stopped due to resource stress testing.

Resolution:
Restarted Apache and restored service availability.
Added CloudWatch alerts to detect service failures.

Prevention:
Enable periodic health checks and auto-recovery for critical services.

Status: Closed

```

---

## 🧠 Skills Demonstrated

- AWS EC2 provisioning
- ALB configuration & health checks
- IAM roles and permissions
- CloudWatch monitoring and alerts
- Linux service troubleshooting
- RCA documentation & ticketing approach

---

## 📂 Repository Structure

```

README.md
notes/
rca-samples/
images/

```

---

## 📌 Future Improvements

- AutoScaling integration
- S3 bucket for centralized log storage
- Bash scripts to automate service recovery
- CI/CD pipeline for deployments

---

## 🏁 Conclusion

This project demonstrates core Cloud Support concepts:
deployment, monitoring, troubleshooting, and incident documentation.
It reflects real-world tasks performed by cloud support and operations engineers.

---

### 💬 Contact

**Bhanu Prasad**  
LinkedIn: https://linkedin.com/in/bhanu-prasad
```
