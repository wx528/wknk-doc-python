# Docker Usage

## Install
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
docker ps
```

## Docker Compose
```
# use default file ./docker-compose.yml
docker compose up

# or  specify the  yml file
docker compose -f docker-compose-monitor.yml up
``` 

## Docker in  WSL

### 1.Enable WSL 2 and Install Ubuntu
```powershell
# Run in PowerShell as Administrator
wsl --install

# Or if WSL is already installed, ensure it's WSL 2
wsl --set-default-version 2

# Install Ubuntu (if not already installed)
wsl --install -d Ubuntu

# Check your WSL version
wsl -l -v
```
### 2.Install Docker Engine in WSL 2
```bash
# Update package list
sudo apt update
sudo apt upgrade -y

# Install prerequisites
sudo apt install -y \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

# Add Docker's official GPG key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Set up the repository
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker Engine
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
### 3.Start Docker Service

```bash
# Start Docker
sudo service docker start

# Check Docker status
sudo service docker status

# Test Docker
sudo docker run hello-world
```

If you see "Hello from Docker!" - it's working!
### 4.Run Docker Without sudo (Important!)

```bash
# Add your user to docker group
sudo usermod -aG docker $USER

# Apply the changes (logout and login, or run:)
newgrp docker

# Test without sudo
docker run hello-world
```

### 5.Auto-Start Docker 
```bash
sudo service docker start
```

### 6.Install Docker Compose
```bash
# Docker Compose is already included with Docker Engine!
docker compose version

# Test it
docker compose --help
```