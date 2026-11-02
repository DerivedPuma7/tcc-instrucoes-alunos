# Importante - após o término
Após o término da tarefa com kubernetes, precisamos limpar o ambiente criado para liberar a porta 8080.

Siga esses passos:

### listar clusters ativos do kind
```bash
kind get clusters
```
> Se os passos anteriores foram seguidos, deve haver um único cluster chamado `tcc-cluster`  

### apagar cluster
```bash
kind delete cluster --name tcc-cluster
```
> Se houver mais de um cluster, apague todos: basta usar o comando acima, substituindo `tcc-cluster` pelo nome do cluster

> Pronto para seguir com a tarefa no Nomad