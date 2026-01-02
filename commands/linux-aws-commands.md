
# 🔧 Linux & AWS Commands Used
## 🔹 EC2 Access & Basic Validation
```bash
ssh -i key.pem ec2-user@<public-ip>
whoami
hostname
uptime
```
---

## 🔹 System Update & Web Server Setup
```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```
---

## 🔹 Service Monitoring & Restart
```bash
sudo systemctl status httpd
sudo systemctl restart httpd
sudo systemctl stop httpd
```
---

## 🔹 CPU & Memory Monitoring (Incident Troubleshooting)
```bash
top
htop
uptime
free -m
nproc
```
---

## 🔹 Disk & Storage Checks
```bash
df -h
du -sh /*
lsblk
```
---

## 🔹 Log Analysis (Root Cause Analysis)
```bash
tail -f /var/log/messages
tail -f /var/log/httpd/access_log
tail -f /var/log/httpd/error_log
journalctl -xe
```
---

## 🔹 Network & Port Validation
```bash
netstat -tulnp
ss -tulnp
curl http://localhost
ping google.com
```
---

## 🔹 File Permissions & Ownership
```bash
ls -l
chmod 755 /var/www/html
chown apache:apache /var/www/html
id
groups
```
---

## 🔹 Load Balancer Testing

```bash
curl http://<load-balancer-dns>
watch curl http://<load-balancer-dns>
```
---

## 🔹 AWS CloudWatch (Monitoring Usage)
```text
Metrics Used:
- CPUUtilization
- StatusCheckFailed
- NetworkIn
- NetworkOut

Alarms Configured:
- CPUUtilization > 80%
- Instance Status Check Failed
```
---

## 🔹 IAM & Security Group Configuration
```text
IAM:
- Created IAM Role for EC2
- Attached CloudWatch monitoring permissions

Security Groups:
- HTTP: Port 80
- SSH: Port 22
```
---
## 🔹 Git & Version Control
```bash
git init
git status
git add .
git commit -m "Added Linux and AWS commands documentation"
git push origin main
```


