- instalar nomad
```bash
curl -fsSLO https://releases.hashicorp.com/nomad/2.0.0/nomad_2.0.0_linux_amd64.zip
curl -fsSLO https://releases.hashicorp.com/nomad/2.0.0/nomad_2.0.0_SHA256SUMS
grep 'linux_amd64.zip' nomad_2.0.0_SHA256SUMS | sha256sum -c -  # esperado: nomad_2.0.0_linux_amd64.zip: OK
unzip -o nomad_2.0.0_linux_amd64.zip nomad
sudo install -o root -g root -m 0755 nomad /usr/local/bin/nomad
rm nomad nomad_2.0.0_linux_amd64.zip nomad_2.0.0_SHA256SUMS
nomad version                                                  # esperado: Nomad v2.0.0 ...
```

- criar cluster
```bash
sudo nomad agent -dev                                                    # irá bloquear o terminal enquanto o processo estiver em execução, continue em outro terminal
```

- acesse http://localhost:4646

> pronto para iniciar a tarefa com nomad
