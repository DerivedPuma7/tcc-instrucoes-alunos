- download docker
```bash
sudo apt-get update
sudo apt-get install -y ca-certificates curl unzip
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] \
https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# Descobre o nome exato do pacote da versão fixa (varia por release do Ubuntu)
VERSION_STRING=$(apt-cache madison docker-ce | awk '{print $3}' | grep -F '29.4.2' | head -1)
echo "$VERSION_STRING"   # exemplo: 5:29.4.2-1~ubuntu.24.04~noble

sudo apt-get install -y docker-ce="$VERSION_STRING" docker-ce-cli="$VERSION_STRING" \
  containerd.io docker-buildx-plugin docker-compose-plugin
sudo apt-mark hold docker-ce docker-ce-cli     # impede atualização automática

sudo usermod -aG docker "$USER"                # depois, faça logout/login (ou: newgrp docker)
docker version --format '{{.Server.Version}}'  # esperado: 29.4.2
docker run --rm hello-world
```
- carregar imagens docker para o ambiente local
```bash
  docker pull nginx:1.30.5
  docker pull httpd:2.4.69
```