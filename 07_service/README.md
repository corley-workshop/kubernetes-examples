# Gestione Service

## Servizio interno al cluster

Un Service di tipologia ClusterIP (predefinito) è un servizio unicamente accessibile dall'interno del Cluster, per crearlo si utilizza il comando:

`kubectl apply -f service_internal.yml`

## Servizio esterno al cluster

Un Service di tipologia NodePort permette di rendere disponibile ad una determinata porta di **ogni Nodo** e all'interno di un Cluster un determinato servizio, per crearlo si utilizza il comando:

`kubectl apply -f service_external_nodeport.yml`
