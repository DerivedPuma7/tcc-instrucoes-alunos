### instalar kind
```bash
curl -fsSLo ./kind https://kind.sigs.k8s.io/dl/v0.26.0/kind-linux-amd64
sudo install -o root -g root -m 0755 ./kind /usr/local/bin/kind
rm ./kind
kind version                                                   # esperado: kind v0.26.0 ...
```

### instalar kubectl
```bash
curl -fsSLO "https://dl.k8s.io/release/v1.32.1/bin/linux/amd64/kubectl"
curl -fsSLO "https://dl.k8s.io/release/v1.32.1/bin/linux/amd64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check      # esperado: kubectl: OK
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
rm kubectl kubectl.sha256
kubectl version --client                                       # esperado: Client Version: v1.32.1
```

### criar cluster: utilize o arquivo de configuração presente neste mesmo diretório
```bash
kind create cluster --config kind-config.yaml --name tcc-cluster # se falhar, tente com sudo (sudo kind create cluster...)
```

### definir contexto do kubectl
```bash
kubectl cluster-info --context kind-tcc-cluster # se falhar, tente com sudo (sudo kind create cluster...)
```

> pronto para iniciar a tarefa com kubernetes
