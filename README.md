# AWS VPC Architecture: Public & Private Subnets with EC2

This project demonstrates my **first AWS architecture setup** where I built a secure VPC with both public and private subnets, configured routing with an Internet Gateway and NAT Gateway, and launched EC2 instances inside each subnet.

---

## 📌 Architecture Overview

- **VPC** – Custom Virtual Private Cloud  
- **Subnets** –  
  - Public Subnet: hosts the public EC2 instance (bastion-like)  
  - Private Subnet: hosts the private EC2 instance (no direct internet access)  
- **Internet Gateway (IGW)** – allows the public subnet to access the internet  
- **NAT Gateway** – allows private subnet instances to reach the internet securely  
- **EC2 Instances** –  
  - Public EC2 (Amazon Linux 2023) with SSH access  
  - Private EC2 (Amazon Linux 2023), accessed via SSH from the public EC2  
- **Key Pairs** – used securely for SSH authentication between public and private EC2  

---

## 🔑 Key Learnings

- Designed and implemented a **VPC with public and private subnets**  
- Configured **route tables** for internet access and secure isolation  
- Used **NAT Gateway** to allow outbound traffic from private subnet  
- Secured private EC2 by accessing it **through the public EC2** (bastion approach)  
- Learned how to manage **key permissions (`chmod 400`)** for private keys  
- Explored **instance metadata service (IMDS)** for retrieving public/private IPs  

---

## 📂 Repository Contents

- `README.md` – Project documentation (this file)  
- `architecture-diagram.png` – Visual diagram of the architecture (add your diagram here)  
- `notes.md` – Step-by-step notes of the setup process  
- `screenshots/` – Screenshots of CLI outputs and successful connections  

---

## 🚀 How It Works

1. Connect to the **Public EC2** via SSH using its public IPv4 address  
2. Copy the **private EC2 key file** to the public instance  
3. From the **public EC2**, SSH into the **private EC2** using its private IP  
4. Private EC2 has **no direct internet access**, but can reach the internet via **NAT Gateway**  

---

## 📝 Notes

This setup is the foundation of many AWS architectures where **public subnets handle external access** and **private subnets secure internal resources**.  

Next steps could include:  
- Hosting a web server in the private subnet  
- Adding RDS in the private subnet  
- Automating setup with Terraform or AWS CLI  

---

## 🙌 Acknowledgements

This project was part of my **AWS learning journey** to understand networking and secure architecture fundamentals.

---

