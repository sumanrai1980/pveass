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

## Technology Stack

* **Core**: PHP, SQLite, JavaScript, HTML, CSS
* **Library Used**: [phpseclib3](https://phpseclib.com/) (Special thanks to the phpseclib project)
* **Helper Code Contributions**: Grok.AI, ChatGPT.AI, and DeepSeek

---

## Deployment with Docker

PVEASS is designed to be easily deployed as a Docker container. You have two main options for deployment: using the pre-built image from Docker Hub or building the image yourself.

### Option 1: Using the Pre-built Docker Image (Recommended)

This is the simplest way to get started. Just pull the official image from Docker Hub and run it.

1.  **Pull the Image**:
    ```bash
    docker pull sumanraic001/pveass:1.0.0
    ```

2.  **Run the Container**:
    ```bash
    docker run -p 8080:80 -v $(pwd)/db:/var/www/html/db sumanraic001/pveass:1.0.0
    ```
    * The `-p 8080:80` flag maps the container's port 80 to your host's port 8080.
    * The `-v $(pwd)/db:/var/www/html/db` flag creates a persistent volume for the SQLite database, ensuring your data is saved even if the container is removed.

3.  **Access the Application**:
    Open your web browser and navigate to `http://localhost:8080` to start using PVEASS.

### Option 2: Building the Image Locally

If you prefer to build the Docker image from the source code yourself, follow these steps.

1.  **Build the Image**:
    Navigate to the root directory of the project and build the Docker image.
    ```bash
    docker build -t pveass:local .
    ```

2.  **Run the Container**:
    You can run the container with a persistent volume to save your data.
    ```bash
    docker run --rm -p 8080:80 -v $(pwd)/db:/var/www/html/db pveass:local
    ```

3.  **Access the Application**:
    Visit `http://localhost:8080` in your web browser.

### Using Docker Compose (Recommended for Development)

For a more streamlined setup, use the provided `docker-compose.yml` file.

1.  **Start the Service**:
    From the project's root directory, simply run the compose command. The `--build` flag will build the image if it doesn't already exist.
    ```bash
    docker compose up -d --build
    ```

2.  **View Logs (Optional)**:
    You can view the container's logs to troubleshoot or monitor its status.
    ```bash
    docker compose logs -f
    ```

---

## Creator Information

* **Created by**: Suman Rai
* **LinkedIn**: [Suman Kumar Rai](https://www.linkedin.com/in/suman-kumar-rai/)
* **E-mail**: sumanrai@live.com

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
