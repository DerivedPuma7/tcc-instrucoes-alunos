# Contexto

Este documento detalha os passos necessários para executar o experimento, além de informações auxiliares importantes.

> **Pré-requisito Universal**
> * **Docker instalado:** Siga os passos presentes em `./pre-requisitos/docker`.

---

## Parte 1 — NGINX

### 1. Pré-requisitos

* **Kubernetes + NGINX:**
  * Instalar `kind`, `kubectl` e criar o cluster: siga os passos presentes em `./pre-requisitos/kubernetes`.
* **Nomad + NGINX:**
  * Instalar o Nomad agent: siga os passos presentes em `./pre-requisitos/nomad`.

> 💡 **Checkpoint:** Nesse ponto, temos os pré-requisitos necessários para fazer a primeira parte do experimento (`nginx`).

---

## Pós-Experimento (Limpeza)

Após o término da Parte 1, precisamos limpar o ambiente e liberar a porta 8080.

* **Limpeza Kubernetes:** Siga os passos presentes em `./pos-requisitos/kubernetes.md`.
* **Limpeza Nomad:** Siga os passos presentes em `./pos-requisitos/nomad.md`.

---

## Parte 2 — HTTPD

### 1. Pré-requisitos

* **Requisito obrigatório:** Ter realizado a limpeza geral citada acima.

* **Kubernetes + HTTPD:**
  * Instalar `kind`, `kubectl` e criar o cluster: siga os passos presentes em `./pre-requisitos/kubernetes`.
* **Nomad + HTTPD:**
  * Instalar o Nomad agent: siga os passos presentes em `./pre-requisitos/nomad`.

> 💡 **Checkpoint:** Nesse ponto, temos os pré-requisitos necessários para fazer a segunda parte do experimento (`httpd`).

# Roteiro
- 19:00 - 19:15: Introdução (Slide de apresentação + assinatura do termo de participação)
- 19:15 - 19:30: Configuração ambiente + separação dos grupos
- 19:30 - 20:00: Parte 1 - NGINX
- > PAUSA 5 MIN - limpeza ambiente + descanso mental
- 20:05 - 20:35: Parte 2 - HTTPD
- 20:35 - 20:40: Coleta de resultados + agradecimentos