# Java Application Deployment on DigitalOcean

**DevOps Portfolio Project | Cloud Infrastructure & Linux Administration**

## Overview

This project demonstrates how to provision an Ubuntu Linux server on DigitalOcean and manually deploy a Java application built with Gradle.

The objective was to gain hands-on experience with Infrastructure as a Service (IaaS), Linux administration, networking, SSH authentication, and application deployment.

The application is a Java/React example provided as part of the TechWorld with Nana DevOps Bootcamp. My contribution focuses on the cloud infrastructure, Linux configuration, security, and deployment process.

## Technology Stack

| Category | Technologies |
|---|---|
| Cloud Provider | DigitalOcean |
| Operating System | Ubuntu Linux |
| Backend | Java |
| Frontend | React |
| Build Tool | Gradle |
| Remote Access | SSH |
| File Transfer | SCP |
| Security | Linux users, sudo, SSH keys, firewall |

## Architecture

```text
Windows Development Machine
          |
          | Gradle Build
          v
     Java JAR File
          |
          | SCP (SSH)
          v
  DigitalOcean Droplet
  +---------------------+
  | Ubuntu Linux        |
  | Java Runtime        |
  | Java Application    |
  | Port 7071           |
  +---------------------+
          |
          | HTTP
          v
      Web Browser
```

## Implementation

### 1. Cloud Server Provisioning

- Created a DigitalOcean account.
- Provisioned an Ubuntu Droplet.
- Configured the cloud firewall to restrict SSH access on port 22 to my IP address.
- Connected to the server using SSH.

### 2. Java Runtime Setup

Installed Java on the Ubuntu server to execute the application.

### 3. Application Build and Deployment

- Built the Java application using Gradle.
- Generated the deployable JAR artifact.
- Transferred the JAR to the remote Ubuntu server using SCP.
- Started the application on the Droplet.
- Configured a firewall rule for application port 7071.
- Verified application access through a web browser.

### 4. Linux User Management and Security

- Created a dedicated non-root Linux user.
- Added the user to the `sudo` group.
- Configured the user's `.ssh` directory.
- Added an SSH public key to `authorized_keys`.
- Applied appropriate permissions to SSH configuration files.

## Useful Linux Commands

**Connect to the server**

```bash
ssh christos@SERVER_IP
```

**Check the current user**

```bash
whoami
```

**Add a user to the sudo group (as root)**

```bash
usermod -aG sudo christos
```

**Check group membership**

```bash
groups christos
```

**Configure SSH directory permissions**

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

**Check the installed Java version**

```bash
java -version
```

## Key Learnings

Through this project, I gained practical experience in:

- Provisioning and accessing cloud infrastructure.
- Understanding Linux users, groups, and permissions.
- Configuring SSH public-key authentication.
- Managing cloud firewall rules.
- Building and deploying Java applications.
- Understanding the relationship between application ports and network access.
- Performing manual application deployment to a remote Linux server.

## Current Limitations and Future Improvements

This project demonstrates a manual deployment workflow rather than a production-ready deployment.

Potential next steps include:

- Containerizing the application with Docker.
- Automating deployment using a CI/CD pipeline.
- Managing the Java application with `systemd`.
- Configuring HTTPS and a reverse proxy.
- Automating infrastructure provisioning using Terraform.
- Adding application monitoring and logging.
