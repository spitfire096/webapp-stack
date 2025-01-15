# Web Application Stack Setup for Local R&D

This project demonstrates the setup of a web application stack for research and development using tools such as MySQL, Tomcat, RabbitMQ, Memcached, and Nginx. The environment is orchestrated using Vagrant, VirtualBox, and Git Bash.

---

## Architecture Overview

### Services:
1. **Database (MySQL)** - Hosted on `db01`.
2. **Memcached** - Hosted on `mc01` for caching.
3. **RabbitMQ** - Hosted on `rmq01` for message queuing.
4. **Tomcat** - Hosted on `app01` for web application deployment.
5. **Nginx** - Hosted on `web01` as a reverse proxy and web server.

### Tools Used:
- **Oracle VM VirtualBox** - Virtualization platform.
- **Vagrant** - Virtual machine orchestration.
- **Git Bash** - Terminal emulator for Windows.
- **Sublime Text** - Code editor for modifying configurations.

### Network:
Each virtual machine is assigned a private IP within the `192.168.56.x` range.

---

## Prerequisites

Ensure the following are installed on your host machine:
1. [Oracle VM VirtualBox](https://www.virtualbox.org/)
2. [Vagrant](https://www.vagrantup.com/)
3. [Git Bash](https://git-scm.com/)
4. [Sublime Text](https://www.sublimetext.com/)

---

## Setup Instructions

### Step 1: Clone the Repository
```bash
# Clone this repository
$ git clone https://github.com/your-repository/web-stack-setup.git
$ cd web-stack-setup
```

### Step 2: Modify the Vagrantfile (if needed)
Use Sublime Text to update the `Vagrantfile` configurations if required.

### Step 3: Launch the Virtual Machines
```bash
# Start the virtual machines
$ vagrant up
```

### Step 4: Verify Virtual Machines
Ensure all VMs are running:
```bash
$ vagrant status
```

### Step 5: Access Services
- **MySQL**: `192.168.56.15`
- **Memcached**: `192.168.56.14`
- **RabbitMQ**: `192.168.56.13`
- **Tomcat**: `192.168.56.12`
- **Nginx**: `192.168.56.11`

### Step 6: SSH into VMs (Optional)
```bash
# SSH into a specific VM
$ vagrant ssh <vm_name>

# Example
$ vagrant ssh db01
```

### Step 7: Stop Virtual Machines
Once done, stop the VMs:
```bash
$ vagrant halt
```

### Step 8: Destroy Virtual Machines (if needed)
```bash
$ vagrant destroy -f
```

---

## Automated Setup Details

The `Vagrantfile` automates the provisioning of:

1. **Database VM**:
   - CentOS Stream 9
   - Allocated 600MB memory.

2. **Memcached VM**:
   - CentOS Stream 9
   - Allocated 600MB memory.

3. **RabbitMQ VM**:
   - CentOS Stream 9
   - Allocated 600MB memory.

4. **Tomcat VM**:
   - CentOS Stream 9
   - Allocated 800MB memory.

5. **Nginx VM**:
   - Ubuntu 22.04 LTS (Jammy Jellyfish)
   - Allocated 800MB memory.

---

## Additional Notes

- **Host Manager Plugin**: Ensure the `vagrant-hostmanager` plugin is installed.
```bash
$ vagrant plugin install vagrant-hostmanager
```

- **Memory Adjustments**: Modify memory allocations in the `Vagrantfile` based on your host machine's resources.

- **Service Configuration**: Configure individual services (MySQL, Memcached, RabbitMQ, Tomcat, Nginx) after provisioning using their respective configuration files.

