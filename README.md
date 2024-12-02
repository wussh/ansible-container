# **alpine/ansible**

A lightweight, multi-architecture Docker image for running **Ansible** based on Alpine Linux.

---

## **Features**

- **Multi-architecture support:** Runs on various platforms (e.g., x86_64, arm64).
- **Lightweight:** Based on Alpine Linux for minimal size and faster performance.
- **Versioned tags:** Each image tag matches an Ansible Core version.

---

## **Getting Started**

### **Pull the Image**
Download the image from Docker Hub:
```bash
docker pull alpine/ansible
```

### **Run Ansible Commands**
Use the following aliases for easier execution:

#### **Ansible Command**
```bash
alias ansible="docker run -ti --rm \
  -v ~/.ssh:/root/.ssh \
  -v ~/.aws:/root/.aws \
  -v $(pwd):/apps \
  -w /apps alpine/ansible ansible"
```
Run an Ansible command:
```bash
ansible <command>
```
Example Ansible command:
```bash
ansible --version
```

#### **Ansible-Playbook Command**
```bash
alias ansible-playbook="docker run -ti --rm \
  -v ~/.ssh:/root/.ssh \
  -v ~/.aws:/root/.aws \
  -v $(pwd):/apps \
  -w /apps alpine/ansible ansible-playbook"
```
Run an Ansible playbook:
```bash
ansible-playbook -i inventory <playbook-file>
```
Example Ansible playbook:
```bash
ansible-playbook --help
```
---

## **Build Locally**

### **Requirements**
Set the following environment variables:
```bash
export CIRCLE_BRANCH=master
export DOCKER_USERNAME=<your-docker-hub-username>
export DOCKER_PASSWORD=<your-docker-hub-password>
```

### **Clone and Build**
1. Clone the repository:
   ```bash
   git clone https://github.com/alpine-docker/multi-arch-libs.git
   cd multi-arch-libs
   ```
2. Build the image:
   ```bash
   ./build.sh ansible
   ```

---

## **Docker Tags**
Tags correspond to Ansible Core versions. Explore available tags on [Docker Hub](https://hub.docker.com/repository/docker/alpine/ansible/tags).

---

## **Dockerfile Source**
The Dockerfile for this image can be found on GitHub:  
[alpine-docker/multi-arch-libs - Ansible Dockerfile](https://github.com/alpine-docker/multi-arch-libs/blob/master/ansible/Dockerfile)
