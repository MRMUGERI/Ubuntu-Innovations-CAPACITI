# Design and Implementation of an IT Infrastructure and Support Solution for Ubuntu Innovations (Pty) Ltd

**Program:** CAPACITI (A Division of UVU Africa) 

**Project Duration:** Four-Week Capstone Project

**Author Role:** IT Technical Support (Junior IT Support Specialist)

**Client Location:** Cape Town, South Africa

---

## 1. Project Overview

This repository contains the complete IT infrastructure design, system administration documentation, cybersecurity governance, and support procedures for **Ubuntu Innovations (Pty) Ltd**, a rapidly growing South African technology startup relocating to a new office in Cape Town.

Designed to support **25 employees** across five core departments, this capstone solution covers hardware and software procurement, segmented network architecture, Linux and Windows operating system administration, role-based access control (RBAC), backup and disaster recovery planning, cybersecurity policies, and helpdesk troubleshooting guides.

### Aligned Certificate Modules

* **Technical Support Fundamentals:** Hardware, operating systems, networking, software, and troubleshooting.


* **The Bits and Bytes of Computer Networking:** Network layer, transport/application layers, networking services, and internet connectivity.


* **Operating Systems and You: Becoming a Power User:** System navigation, users and permissions, package management, filesystems, and process management.


* **System Administration and IT Infrastructure Services:** Network/infrastructure services, software/platform services, directory services, and data recovery/backups.


* **IT Security: Defense Against the Digital Dark Arts:** Security threats, cryptology, authentication/authorization/accounting (AAA), network security, and defense in depth.


* **Accelerate Your Job Search with AI:** AI-assisted workflow streamlining and career readiness portfolio preparation.



---

## 2. Business Case & Organizational Structure

Ubuntu Innovations (Pty) Ltd requires a secure, scalable, and fully documented IT environment for its 25 staff members:

| Department | Number of Employees | Security Group | Authorized Shared Folder Access |
| --- | --- | --- | --- |
| **Executive Management** | 3

 | `mgmt_grp`<br> | `/Company/Management` (Full access across directories)

 |
| **Finance** | 4

 | `finance_grp`<br> | `/Company/Finance` & `/Company/Public`<br> |
| **Human Resources** | 3

 | `hr_grp`<br> | `/Company/HR` & `/Company/Public`<br> |
| **Sales and Marketing** | 7

 | `sales_grp`<br> | `/Company/Sales` & `/Company/Public`<br> |
| **Software Development** | 8

 | `dev_grp`<br> | `/Company/Development` & `/Company/Public`<br> |
| **Total Employees** | **25**<br> | — | — |

---

## 3. Infrastructure Architecture Summary

### 3.1 Hardware Inventory

| Asset | Quantity | Specification | Business Justification |
| --- | --- | --- | --- |
| **Desktop Computers** | 20

 | Intel Core i5, 16GB RAM, 512GB SSD

 | General office use

 |
| **Laptops** | 5

 | Intel Core i7, 16GB RAM

 | Mobility for management

 |
| **Router** | 1

 | Business-grade firewall router

 | Internet connectivity and perimeter security

 |
| **Switch** | 1

 | 24-port Gigabit managed switch

 | Internal wired networking and VLAN segmentation

 |
| **Wireless Access Points** | 2

 | Dual-band Wi-Fi 6

 | High-speed wireless office coverage

 |
| **Network Printers** | 2

 | Laser printers

 | Shared departmental printing

 |
| **NAS Device** | 1

 | 8TB RAID storage

 | Centralized backups and shared file storage

 |
| **UPS** | 2

 | 1500VA

 | Power protection against outages

 |

### 3.2 Network Subnets & IP Addressing Plan

* **Servers & NAS Subnet (`192.168.10.0/24`):** Isolates the 8TB RAID NAS device and core infrastructure services.


* **Wired User Devices Subnet (`192.168.20.0/24`):** Connects the 20 desktop workstations via the 24-port Gigabit managed switch.


* **Network Printers Subnet (`192.168.30.0/24`):** Segments the 2 shared laser network printers.


* **Wi-Fi Subnet (`192.168.40.0/24`):** Serves the 5 management laptops and wireless endpoints via the 2 dual-band Wi-Fi 6 access points.



---

## 4. Repository Structure & Deliverables Checklist

This repository is organized to map directly to the **19 required Capstone Project Deliverables** and the **4-Week Project Plan**:

* `01_Executive_Summary/` – Project scope and executive overview.


* `02_Business_Requirements_Analysis/` – Analysis of organizational structure, required applications, data security, connectivity, and operational challenges.


* `03_Hardware_Inventory/` – Hardware Inventory Spreadsheet (`Hardware_Inventory.xlsx`) with specifications and justifications.


* `04_Software_and_Licensing_Plan/` – Software Inventory, Deployment Plan, update procedures, and licensing matrix.


* `05_Network_Diagram/` – High-level and logical network topologies (`Network_Topology.drawio` / `.png`) showing ISP, firewall router, switch, Wi-Fi 6 APs, user devices, printers, and NAS.


* `06_IP_Addressing_Plan/` – Subnet allocation table across Servers, User Devices, Printers, and Wi-Fi.


* `07_User_and_Permissions_Matrix/` – Department security group mappings (`mgmt_grp`, `finance_grp`, `hr_grp`, `sales_grp`, `dev_grp`).


* `08_Shared_Folder_Structure/` – Directory layout for `/Company/Public`, `/Company/Finance`, `/Company/HR`, `/Company/Sales`, `/Company/Development`, and `/Company/Management`.


* `09_OS_Administration_Guide/` – PC setup guidelines and Ubuntu Linux Command-Line Administration Guide (`pwd`, `ls`, `cd`, `mkdir`, `touch`, `chmod`, `chown`, `ps`, `top`, `apt install`).


* `10_Backup_and_Disaster_Recovery_Plan/` – Daily incremental, weekly full, and monthly cloud archive backup schedules with defined RTO and RPO targets.


* `11_Cybersecurity_Policy/` – Password complexity, MFA, device encryption, antivirus/EDR standards, patch management, and Acceptable Use Policy (AUP).


* `12_Risk_Assessment_Matrix/` – Likelihood, impact, and mitigation strategies for Phishing, Ransomware, Hardware Failure, and Power Outages.


* `13_Incident_Response_Plan/` – Six-phase response workflow (Detection, Reporting, Containment, Eradication, Recovery, Lessons Learned) and Security Awareness Training outline.


* `14_Troubleshooting_Guide/` – Helpdesk ticketing SOP and structured runbooks for Desktop Not Powering On, No Internet Connectivity, and Printer Offline scenarios.


* `15_Career_Readiness_Materials/` – Tailored one-page IT Support CV, Cover Letter, LinkedIn Summary, and 10 IT Support Interview Q&As.


* `16_Final_Presentation_and_Report/` – Consolidated Final Project Report (`.pdf`), 10–15 minute Presentation Deck (`.pptx`), and final archive (`Awonke_Philibane_ITSupport_Capstone.zip`).



---

## 5. Quick-Start: Linux Directory & Permissions Setup

To replicate the Ubuntu Innovations shared directory structure and group permissions on an Ubuntu Linux server or VirtualBox environment, run the following commands as demonstrated in the **Operating System Administration Guide** (Week 2, Task 1–3):

```bash
# 1. Verify current working directory and list contents
pwd
ls -la

# 2. Create the core shared directory hierarchy
sudo mkdir -p /Company/Public /Company/Finance /Company/HR /Company/Sales /Company/Development /Company/Management

# 3. Create department security groups
sudo groupadd mgmt_grp
sudo groupadd finance_grp
sudo groupadd hr_grp
sudo groupadd sales_grp
sudo groupadd dev_grp

# 4. Assign group ownership to departmental folders
sudo chown -R :mgmt_grp /Company/Management
sudo chown -R :finance_grp /Company/Finance
sudo chown -R :hr_grp /Company/HR
sudo chown -R :sales_grp /Company/Sales
sudo chown -R :dev_grp /Company/Development

# 5. Enforce least-privilege directory permissions
sudo chmod 770 /Company/Management /Company/Finance /Company/HR /Company/Sales /Company/Development
sudo chmod 775 /Company/Public

# 6. Create a verification readme file and monitor system processes
sudo touch /Company/Public/Welcome_Ubuntu_Innovations.txt
ps aux
top

```

---

## 6. Tools & Technologies Used

| Tool | Project Purpose |
| --- | --- |
| **Microsoft Word / Google Docs** | Technical policies, reports, and procedural documentation

 |
| **Microsoft Excel / Google Sheets** | Hardware/software inventories, IP plans, and risk/permission matrices

 |
| **Draw.io** | Network topology and subnet architecture diagrams

 |
| **PowerPoint / Canva** | Final stakeholder presentation slides

 |
| **VirtualBox & Ubuntu Linux** | Operating system administration practice and permission testing

 |
| **GitHub** | Version control, repository hosting, and project submission

 |
| **AI Tools (ChatGPT / Gemini)** | AI-assisted documentation structuring and career readiness preparation

 |
