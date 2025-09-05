# PVEASS: Proxmox Virtual Environment Assistant

PVEASS (Proxmox Virtual Environment Assistant) is a powerful, web-based application designed to simplify disaster recovery and failover management in **Proxmox Virtual Environment (PVE)**. Built with user-friendliness and automation in mind, PVEASS empowers Proxmox administrators to prepare, manage, and recover their infrastructure with ease.

## Key Features

* **Seamless Integration with Proxmox**: Add failover sites and hosts effortlessly using an API Token and API Token Secret.
* **PBS (Proxmox Backup Server) Support**: Connect and manage PBS hosts directly through the application.
* **ZFS Storage Management**: Create and manage ZFS storage on your Proxmox hosts with just a few clicks.
* **Storage Mapping**: Easily map storage across environments for better consistency and availability.
* **VM & Container Restore**: Restore virtual machines and containers to the required hosts in case of a disaster.

## Why PVEASS?

In mission-critical environments, downtime is not an option. PVEASS helps administrators build and maintain standby failover servers, ensuring business continuity and minimizing downtime during unexpected failures.

## System Requirements

To ensure optimal performance and a smooth user experience, please ensure your system meets the following minimum requirements:

* **OS**: Ubuntu Server
* **CPU**: 2 Cores
* **RAM**: 8 GB
* **Storage**: 20 GB of free disk space
* **Network**: A stable and fast network connection for efficient data transfer and communication with Proxmox hosts.

## Technology Stack

* **Core**: PHP, SQLite, JavaScript, HTML, CSS
* **Library Used**: [phpseclib3](https://phpseclib.com/) (Special thanks to the phpseclib project)
* **Helper Code Contributions**: Grok.AI, ChatGPT.AI, and DeepSeek

---

## Getting Started

This guide will walk you through the process of setting up and running PVEASS using a pre-built Docker image. This is the recommended method for quick and easy deployment. 

### How to Install and Run

1.  **Pull the Image**:
    Pull the official PVEASS image from Docker Hub.
    ```bash
    docker pull sumanraic001/pveass:1.0.0
    ```

2.  **Run the Container**:
    Run the container with a persistent volume to ensure your configuration and database are saved.
    ```bash
    docker run -p 8080:80 -v $(pwd)/db:/var/www/html/db sumanraic001/pveass:1.0.0
    ```
    * The `-p 8080:80` flag maps the container's internal web server port (80) to port 8080 on your host machine.
    * The `-v $(pwd)/db:/var/www/html/db` flag creates a data volume, so all your application data (like the SQLite database) will persist even if the container is stopped or removed.

3.  **Access the Application**:
    Once the container is running, open your web browser and navigate to `http://localhost:8080` to begin using PVEASS.

---

## 📖 Tutorial

A step-by-step **Tutorial Guide** with screenshots is available inside the repository under the [`Tutorial`](Tutorial/) folder.  

👉 You can also view the rendered guide directly here:  
[**Open Tutorial in Browser**](https://sumanrai1980.github.io/pveass/Tutorial/index.html){:target="_blank"}

---

## Creator Information

* **Created by**: Suman Rai
* **LinkedIn**: [Suman Kumar Rai](https://www.linkedin.com/in/suman-kumar-rai/)
* **E-mail**: sumanrai@live.com

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
