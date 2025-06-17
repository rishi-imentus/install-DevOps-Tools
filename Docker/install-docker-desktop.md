### Steps to Install Docker Desktop on Ubuntu 24.04  

#### 1. *Update System Packages*  
Start by updating your system:  
```bash
sudo apt update && sudo apt upgrade -y
```  

#### 2. *Install Required Dependencies*  
Install the required dependencies for Docker Desktop:  
```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```  

#### 3. *Install Docker Engine*  
Add Docker’s official GPG key and repository:  
```bash
curl -fsSL https://download.docker.com/linux/ubu... | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list - /dev/null
```  
Then install Docker Engine:  
```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io -y
```  

#### 4. *Download Docker Desktop Package*  
Download the latest `.deb` package for Docker Desktop:  
```bash
wget https://desktop.docker.com/linux/main...[version]-amd64.deb
```  
Replace `[version]` with the latest version number available on Docker’s official website.  

#### 5. *Install Docker Desktop*  
Install the downloaded package using:  
```bash
sudo apt install ./docker-desktop-[version]-amd64.deb
```  

#### 6. *Add Your User to the Docker Group*  
Ensure non-root users can access Docker:  
```bash
sudo usermod -aG docker $USER
```  
Restart your system for the changes to take effect.  

#### 7. *Start Docker Desktop*  
Launch Docker Desktop from your applications menu or using the terminal:  
```bash
systemctl --user start docker-desktop
```  

---

Verify Installation  
Confirm Docker Desktop is running:  
```bash
docker --version
docker-compose --version
