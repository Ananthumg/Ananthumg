<div align="center">

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│        ☁️  ANANTHAKRISHNAN M G                          │
│        Linux · AWS · Cloud · DevOps                     │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ananthu.mg.careers@gmail.com)
[![Location](https://img.shields.io/badge/Thrissur%2C%20Kerala-India-FF9933?style=for-the-badge&logo=googlemaps&logoColor=white)](#)

</div>

---

## 👨‍💻 About Me

> *"Infrastructure that scales, systems that don't sleep."*

Cloud and System Engineer with hands-on experience designing and deploying **production-grade AWS infrastructure** from scratch. I've built secure multi-AZ WordPress deployments with Auto Scaling, managed Linux server environments with cPanel/WHM, and hardened systems against real-world threats. I'm passionate about making infrastructure **reliable, secure, and self-healing**.

- 🔭 Currently working as **Quality Engineer @ Sasmos HET Technologies, Bengaluru**
- 🌱 Actively building expertise in **AWS Cloud Engineering & DevOps**
- 💡 Strong believer in **infrastructure-as-practice** — learning by building real things
- 📫 Reach me at: **ananthu.mg.careers@gmail.com** | **+91 7356706501**

---

## 🛠️ Tech Stack

### ☁️ Cloud Platforms
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=FF9900)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white)
![S3](https://img.shields.io/badge/S3-569A31?style=flat-square&logo=amazons3&logoColor=white)
![RDS](https://img.shields.io/badge/RDS-527FFF?style=flat-square&logo=amazonrds&logoColor=white)
![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-8C4FFF?style=flat-square&logo=amazonaws&logoColor=white)
![Route53](https://img.shields.io/badge/Route53-8C4FFF?style=flat-square&logo=amazonaws&logoColor=white)
![ECS](https://img.shields.io/badge/ECS-FF9900?style=flat-square&logo=amazonaws&logoColor=white)

### 🐧 Server & OS
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=flat-square&logo=apache&logoColor=white)
![NGINX](https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=nginx&logoColor=white)
![cPanel](https://img.shields.io/badge/cPanel-FF6C2C?style=flat-square&logo=cpanel&logoColor=white)

### 🌐 Web & CMS
![WordPress](https://img.shields.io/badge/WordPress-21759B?style=flat-square&logo=wordpress&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)

### 🔐 Security & Monitoring
![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4F8B?style=flat-square&logo=amazonaws&logoColor=white)
![IAM](https://img.shields.io/badge/IAM-DD344C?style=flat-square&logo=amazonaws&logoColor=white)
![SSL/TLS](https://img.shields.io/badge/SSL%2FTLS-00B388?style=flat-square&logo=letsencrypt&logoColor=white)

---

## 🚀 Featured Project

<div align="center">

### ☁️ High Availability WordPress & Static Website Deployment on AWS

**A fully production-grade, multi-AZ AWS infrastructure built end-to-end from scratch**

[![WordPress Live](https://img.shields.io/badge/🌐%20WordPress%20Live-wordpress.ananthu.shop-21759B?style=for-the-badge)](https://wordpress.ananthu.shop/)
[![Static Site](https://img.shields.io/badge/📄%20Static%20Site-static.ananthu.shop-FF9900?style=for-the-badge)](https://static.ananthu.shop/)

</div>

---

### 🏗️ Architecture Overview

```
                          INTERNET
                             │
                    ┌────────▼────────┐
                    │   Route 53      │  DNS Management
                    │  ananthu.shop   │
                    └──┬──────────┬───┘
                       │          │
              ┌─────────▼──┐  ┌───▼──────────┐
              │    ALB      │  │  CloudFront  │
              │ HTTPS:443   │  │     CDN      │
              │ HTTP→HTTPS  │  └──────┬───────┘
              └──────┬──────┘         │
                     │           ┌────▼───┐
         ┌───────────▼──────┐    │  S3    │  Static Site
         │  Auto Scaling     │    │Bucket  │  static.ananthu.shop
         │  Group (ASG)      │    └────────┘
         │  Min:1 / Max:2    │
         └──┬─────────────┬──┘
            │             │
    ┌────────▼──┐   ┌──────▼────┐
    │ EC2 (AZ-a)│   │ EC2 (AZ-b)│   Amazon Linux 2023
    │ us-east-1a│   │ us-east-1b│   + WordPress + SSM
    └────────┬──┘   └──────┬────┘
             │             │
         ┌───▼─────────────▼───┐
         │      EFS Mount      │  Shared /var/www/html
         │  fs-0615122637d534  │
         └─────────┬───────────┘
                   │
         ┌─────────▼───────────┐
         │   RDS MySQL (Private│  ananthu-rds-exam-2-aws
         │   Subnet - No Public│  Multi-AZ Private Subnets
         │   Access)           │
         └─────────────────────┘

VPC CIDR: 10.152.50.0/23
  ├── Public  Subnet A: 10.152.50.0/25   (us-east-1a)
  ├── Public  Subnet B: 10.152.50.128/25 (us-east-1b)
  ├── Private Subnet C: 10.152.51.0/25   (us-east-1c)
  └── Private Subnet D: 10.152.51.128/25 (us-east-1d)
```

---

### 📋 Step-by-Step Implementation

<details>
<summary><b>Step 1 — VPC & Network Architecture</b></summary>

**Goal:** Build a secure, isolated network foundation with public and private subnets across two Availability Zones.

**What was done:**
- Created a custom VPC with CIDR block `10.152.50.0/23` (512 IPs)
- Provisioned **4 subnets** across **4 Availability Zones**:
  - `ananthu-public-SNa` → `10.152.50.0/25` (us-east-1a)
  - `ananthu-public-SNb` → `10.152.50.128/25` (us-east-1b)
  - `ananthu-private-SNc` → `10.152.51.0/25` (us-east-1c)
  - `ananthu-private-SNd` → `10.152.51.128/25` (us-east-1d)
- Deployed an **Internet Gateway (IGW)** and attached it to the VPC
- Configured **two Route Tables**:
  - `ananthu-public-RT` → associated with both public subnets, routes `0.0.0.0/0` to IGW
  - `ananthu-private-RT` → associated with both private subnets, no public route
- Created **dedicated Security Groups** for each tier:
  - `ananthu-ALB-SG` — ALB traffic
  - `ananthu-EC2-SG` — EC2 instances
  - `ananthu-NFS-EFS-SG` — EFS file system
  - `ananthu-RDS-SG` — MySQL database

**Why this matters:** Placing compute in public subnets and the database in private subnets follows AWS's defence-in-depth principle — the RDS instance is completely unreachable from the internet, even if an EC2 instance were compromised.

</details>

<details>
<summary><b>Step 2 — RDS MySQL in Private Subnets</b></summary>

**Goal:** Deploy a managed, secure database that is inaccessible from the internet.

**What was done:**
- Launched an **Amazon RDS MySQL** instance (`ananthu-rds-exam-2-aws`) inside the private subnet group
- Configured the instance with:
  - **VPC:** `ananthu-vpc`
  - **Subnet Group:** `ananthu-sng-rds` (private subnets only)
  - **Publicly Accessible:** No
  - **Port:** 3306
  - **Security Group:** `ananthu-RDS-SG` (allows inbound only from EC2 security group)
- Subnet placement spans two private AZs for fault tolerance

**Why this matters:** By placing RDS exclusively in private subnets with no public access flag, the database layer is shielded behind the EC2 tier. Only the application servers can reach port 3306.

</details>

<details>
<summary><b>Step 3 — EC2 Launch with SSM (No SSH Keys)</b></summary>

**Goal:** Launch a compute instance using AWS Systems Manager instead of traditional SSH key pairs, improving security posture.

**What was done:**
- Launched an **Amazon Linux 2023** EC2 instance inside `ananthu-vpc` on a public subnet
- Attached an **IAM role with SSM policy** — this eliminates the need for SSH key pairs entirely
- Connected to the instance via **AWS Session Manager** (browser-based shell), with full auditability of all session activity

**Why this matters:** SSM removes the attack surface of open port 22, avoids key management overhead, and every session is logged to CloudWatch — a security and compliance best practice.

</details>

<details>
<summary><b>Step 4 — EFS Mount & WordPress Installation</b></summary>

**Goal:** Use a shared, persistent file system so all EC2 instances in the Auto Scaling Group serve the same WordPress files.

**What was done:**
- Created **Amazon EFS** (`ananthu-EFS-exam-2-AWS`, fs-0615122637d534178)
  - Performance mode: General Purpose | Throughput: Bursting | Encrypted at rest | Auto backups: On
- Mounted EFS on the EC2 instance at `/var/www/html` with a **permanent fstab entry** using `_netdev` flag
- Installed WordPress and all dependencies — all files stored on the EFS mount
- Configured `wp-config.php` pointing `DB_HOST` to the RDS endpoint
- Verified WordPress loaded correctly via the EC2 public IP

**Why this matters:** Without shared EFS, each EC2 instance behind a load balancer would have independent file storage. Any upload or plugin installed on one node would be missing on the other. EFS makes all nodes stateless and identical.

</details>

<details>
<summary><b>Step 5 — AMI Creation & Multi-AZ Validation</b></summary>

**Goal:** Bake a golden AMI from the configured instance to enable repeatable, identical deployments across AZs.

**What was done:**
- Created a custom **AMI** (`ananthu-exam-2-aws-ami-wordpress`) from the fully configured EC2 instance
- Launched a **second EC2 instance** in `ananthu-public-SNb` (us-east-1b) from the same AMI
- Verified WordPress loaded correctly from the second instance's public IP, confirming EFS and RDS connectivity worked cross-AZ

**Why this matters:** This validates true high availability. If us-east-1a fails, the identical instance in us-east-1b continues serving traffic, reading from the same EFS and RDS — zero downtime.

</details>

<details>
<summary><b>Step 6 — Application Load Balancer with HTTPS (ACM)</b></summary>

**Goal:** Place a managed load balancer in front of both EC2 instances, enforce HTTPS, and terminate SSL at the ALB layer.

**What was done:**
- Created **ALB** (`ananthu-exam-2-ALB`) — Internet-facing, spanning both public subnets
- Provisioned SSL/TLS certificate via **ACM** for `wordpress.ananthu.shop` — Status: Issued ✅
- Configured two listeners:
  - `HTTPS:443` → forwards to target group (3 healthy instances)
  - `HTTP:80` → 301 permanent redirect to HTTPS
- Target group health checks confirmed all registered instances healthy

**Why this matters:** The ALB distributes traffic with automatic health checks, removing unhealthy instances without intervention. ACM handles automatic certificate renewal — no manual SSL management ever needed.

</details>

<details>
<summary><b>Step 7 — Auto Scaling Group for Self-Healing Infrastructure</b></summary>

**Goal:** Ensure the infrastructure automatically recovers from instance failures and can scale under load.

**What was done:**
- Created **ASG** (`ananthu-ASG-exam-2`) with:
  - Desired: **1** | Min: **1** | Max: **2**
  - Launch template based on the WordPress AMI
  - Attached to the ALB target group
- Confirmed the ASG launched and registered an instance with the ALB successfully

**Why this matters:** If an EC2 instance fails health checks, the ASG terminates and replaces it automatically — the site stays online with zero manual intervention. Under traffic spikes, it scales out to the defined maximum.

</details>

<details>
<summary><b>Step 8 — Route 53 DNS & Live Domain</b></summary>

**Goal:** Point a human-readable domain to the ALB, making the site live at `https://wordpress.ananthu.shop`.

**What was done:**
- Configured Route 53 hosted zone for `ananthu.shop`
- Created a **CNAME record**: `wordpress.ananthu.shop` → ALB DNS name
- Verified the site is live, loading with a valid HTTPS certificate

🌐 **Live:** [https://wordpress.ananthu.shop/](https://wordpress.ananthu.shop/)

</details>

<details>
<summary><b>Step 9 — S3 Static Website + CloudFront CDN with OAC</b></summary>

**Goal:** Host a static website on S3 with global CDN delivery, blocking all direct S3 bucket access.

**What was done:**
- Created S3 bucket (`static.ananthu.shop`) with versioning enabled, uploaded `index.html`
- Created **CloudFront distribution** with **Origin Access Control (OAC)** — content accessible only via CloudFront, never directly from S3
- Applied bucket policy granting access exclusively to the CloudFront service principal
- Created CNAME record: `static.ananthu.shop` → CloudFront distribution domain
- **Confirmed:** Direct S3 URL returns `AccessDenied` — OAC working correctly ✅

🌐 **Live:** [https://static.ananthu.shop/](https://static.ananthu.shop/)

</details>

---

### 🧰 AWS Services Used

| Service | Purpose |
|---|---|
| **VPC** | Isolated virtual network with public/private subnets |
| **EC2** | Application servers running WordPress |
| **EFS** | Shared persistent file system for WordPress files |
| **RDS MySQL** | Managed relational database in private subnets |
| **ALB** | Load balancing + HTTPS termination |
| **ASG** | Auto Scaling for self-healing infrastructure |
| **ACM** | Free SSL/TLS certificate management |
| **SSM** | Keyless, auditable EC2 access |
| **Route 53** | DNS management for ananthu.shop |
| **S3** | Static website hosting |
| **CloudFront** | Global CDN with OAC-protected S3 origin |
| **AWS Backup** | Automated backup policies |
| **IAM** | Role-based access control |

---

## 💼 Professional Experience

```
📅 Dec 2025 – Present   Quality Engineer          @ Sasmos HET Technologies, Bengaluru
📅 Jul – Sep 2025       System Engineer Intern    @ EPI-USE, Kochi
📅 May – Jun 2025       Server Administrator      @ HashRoot, Kochi
📅 Oct 2023 – Dec 2024  Network Support Engineer  @ Modwin Networks (South Indian Bank HQ)
📅 Sep 2022 – May 2023  Networking Intern         @ Synnefo Solutions, Kochi
```

---

## 📊 GitHub Stats

<div align="center">

![Ananthakrishnan's GitHub Stats](https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=dark&hide_border=true&bg_color=0d1117&title_color=FF9900&icon_color=FF9900&text_color=c9d1d9)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_GITHUB_USERNAME&layout=compact&theme=dark&hide_border=true&bg_color=0d1117&title_color=FF9900&text_color=c9d1d9)

</div>

---

## 📚 Education

- 🎓 **Diploma in Electronics & Communication Engineering** — Government Polytechnic College (2019–2022)
- 📖 **Higher Secondary — Bio Science** — Government Higher Secondary School (2018–2019)

---

<div align="center">

**📌 Want to see my AWS project in detail?**

[![View Project](https://img.shields.io/badge/📂%20View%20AWS%20Project-Pinned%20Repository-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](#)

---

*"Build things. Break things. Fix things. Repeat."*

![Profile Views](https://komarev.com/ghpvc/?username=YOUR_GITHUB_USERNAME&color=FF9900&style=flat-square&label=Profile+Views)

</div>
