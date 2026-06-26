# 🌐 Day 1: Cloud Infrastructure, Remote Access & Enterprise AWS EC2 Deployment

### 🏗️ 1. Cloud Virtualization Architecture
* **Under the Hood:** Explored how AWS manages physical hardware using hypervisors (Type-1 Hypervisors like AWS Nitro/Xen) to carve out isolated Virtual Machines (VMs) for users.
* **EC2 Instance Lifecycle:** Learned the mechanics of provisioning an Ubuntu 24.04 LTS compute node on multi-tenant hardware resources, selecting standard architectures (`x86_64`), and observing server initialization.

### 🔒 2. Enterprise Network Security & Isolation
* **Security Groups (Stateful Firewalls):** Handled infrastructure security by implementing network filters at the hypervisor level. Configured strict inbound rules:
  * **SSH (Port 22):** Open exclusively for secure terminal management.
  * **HTTP/HTTPS (Ports 80/443):** Prepared network paths for future web traffic deployments.
* **Stateful Firewall Behavior:** Learned that incoming traffic allowed through a Security Group automatically permits the corresponding outgoing traffic, regardless of outbound rules.

### 🔑 3. Asymmetric Cryptography & Remote Management
* **Key-Pair Architecture (`.pem`):** Practiced secure remote authentication utilizing RSA asymmetric key pairs rather than weak passwords.
* **Cryptographic Handshake:** The public key is embedded in the server's `/home/ubuntu/.ssh/authorized_keys`, while the private key remains secure on the host.
* **Access Execution:** Established an encrypted terminal session utilizing OpenSSH:
  ```bash
  ssh -i "your-key.pem" ubuntu@<Public-IP>
