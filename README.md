# Nginx Static Mini Profile Page Deployment

## Project Overview

This project demonstrates how to deploy an Ubuntu Focal 64 virtual machine using Vagrant and serve a static mini profile web page using **Nginx**.

The web page is built with HTML and CSS and hosted locally inside the VM.

---

## Technologies Used

* Ubuntu Focal 64
* **Vagrant**
* **Nginx**
* HTML
* Vim

---

## Setup Instructions

### 1. Initialize Vagrant

```bash
mkdir nginx-vm
cd nginx-vm
vagrant init ubuntu/focal64
```

Optional: Configure a private network IP inside the `Vagrantfile`:

```ruby
config.vm.network "private_network", ip: "192.168.56.10"
```

Start the VM:

```bash
vagrant up
vagrant ssh
```

---

### 2. Update and Install Nginx

```bash
apt update
apt upgrade -y
apt install nginx -y
```

---

### 3. Deploy the Static Profile Page

Navigate to the web root:

```bash
cd /var/www/html
rm index.nginx-debian.html
vim index.html
```

Add the HTML and CSS mini profile code, then save and exit.

Restart Nginx:

```bash
systemctl restart nginx
systemctl enable nginx
```

---

## Access the Web Page

Open a browser on your host machine and visit:

```
http://192.168.56.10
```

You should see the mini profile page served by Nginx.

---

## What This Project Demonstrates

* VM provisioning with Vagrant
* Package management using apt
* Installing and configuring Nginx
* Serving static web content
* Editing files using Vim

---
