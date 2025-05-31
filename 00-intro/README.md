# Pré-requisitos para o Lab DevOps Automation

Este documento lista os pré-requisitos necessários para acompanhar todos os módulos do curso DevOps Automation. Escolha seu sistema operacional e siga o passo a passo correspondente para garantir que seu ambiente está pronto.

---

## 🔧 Se você está usando **Ubuntu (nativo ou em VM)**

### 1. Atualize o sistema e instale ferramentas básicas:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y git curl unzip software-properties-common gnupg unzip
sudo apt update && sudo apt upgrade -y
sudo apt install -y git curl unzip software-properties-common gnupg
```

### 2. Instale o Git e configure:

```bash
sudo apt install git -y
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
git --version
```

### 3. Instale o Docker:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
newgrp docker
sudo docker run hello-world
```

### 4. Instale o AWS CLI:

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
```

### 5. Instale o Azure CLI:

```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
az version
```

### 7. Instale o Terraform:

```bash
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update && sudo apt install terraform -y
terraform -version
```

### 8. Instale o Ansible:

```bash
sudo apt install ansible -y
ansible --version
```

### 9. Instale o kubectl e o watch:

```bash
curl -LO "https://dl.k8s.io/release/$(curl -Ls https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client

sudo apt install -y watch
watch --version
```

### 11. Instale o VS Code:

Baixe em: [https://code.visualstudio.com/](https://code.visualstudio.com/)
E instale as extensões: Docker, Terraform, YAML, GitHub Pull Requests

---

## 💻 Se você está usando **Windows com WSL 2 (recomendado)**

### 1. Instale o WSL:

```powershell
wsl --install
```

> Isso instala o WSL 2 com Ubuntu automaticamente (Windows 11).

### 2. Se necessário, instale manualmente:

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

* Reinicie o computador
* Baixe o kernel: [https://aka.ms/wsl2kernel](https://aka.ms/wsl2kernel)
* Defina o WSL 2 como padrão:

```powershell
wsl --set-default-version 2
```

* Instale o Ubuntu pela Microsoft Store

### 3. Abra o Ubuntu e siga os mesmos passos do Ubuntu nativo acima para instalar Git, Docker, AWS CLI, etc.

### 4. Instale o Docker Desktop no Windows:

[https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)

> Marque a opção para integração com WSL

### 5. Instale o Visual Studio Code e a extensão **Remote - WSL**

[https://code.visualstudio.com/](https://code.visualstudio.com/)

---

## 🍎 Se você está usando **macOS**

### 1. Instale o Homebrew:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 2. Instale ferramentas:

```bash
brew install git terraform ansible node docker awscli azure-cli
```

### 3. Verifique versões:

```bash
git --version
terraform -version
ansible --version
docker --version
aws --version
az version
```

### 4. Instale o Docker Desktop:

[https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)

### 5. Instale o Visual Studio Code:

[https://code.visualstudio.com/](https://code.visualstudio.com/)

### 6. Instale as extensões:

* Docker
* Terraform
* YAML
* GitHub Pull Requests

---

## Com tudo pronto...

Você poderá:

* Clonar repositórios GitHub
* Rodar containers
* Executar comandos CLI em AWS e Azure
* Criar recursos com Terraform e Ansible

Está tudo pronto para começar os labs do curso DevOps Automation!
