# Jenkins Custom Egg for Pterodactyl

This repository contains a custom Pterodactyl egg for Jenkins. This egg allows you to easily set up and run a Jenkins server within the Pterodactyl panel.
If you find any ways to improve this egg or encounter any issues, please feel free to contact me.


## Features

- Jenkins setup using a Docker container with Java 17.
- Automatic download and installation of the latest stable Jenkins WAR file.
- Simple startup configuration to launch Jenkins on the specified server port.

## Installation

1. **Import the Egg**:
   - Go to your Pterodactyl admin panel.
   - Navigate to `Nests` -> `Eggs` -> `Import Egg`.
   - Upload the provided JSON file.

2. **Create a New Server**:
   - Go to `Servers` -> `Create New`.
   - Select the newly imported Jenkins egg.
   - Fill out the required server details and create the server.

3. **Start the Server**:
   - After the server is created, start it from the Pterodactyl panel.
   - Jenkins will be downloaded and installed automatically during the first startup.

## Usage

- **Access Jenkins**:
  - Open your browser and navigate to the IP address and port of your Pterodactyl server.
  - Complete the Jenkins setup wizard as per the instructions provided by Jenkins.

- **Manage Jenkins**:
  - Use the Jenkins web interface to manage jobs, plugins, and other configurations.

## Configuration

- **Startup Command**:
  - The server starts Jenkins using the following command:
    ```bash
    java -jar /home/container/jenkins.war --httpPort={{SERVER_PORT}}
    ```
- **Logs**:
  - Jenkins logs can be found in the `logs/latest.log` file within the server directory.

## Customization

- **Docker Image**:
  - This egg uses the `ghcr.io/pterodactyl/yolks:java_17` Docker image. You can change this to another image if required.
- **Installation Script**:
  - The installation script downloads the latest stable Jenkins WAR file from the official Jenkins website. You can modify the script if you need a different version or additional setup steps.
