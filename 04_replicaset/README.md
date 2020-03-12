# Gestione ReplicaSet

## Lanciare un ReplicaSet nel cluster

Per lanciare il ReplicaSet di questo esempio nel cluster possiamo utilizzare il comando:

`kubectl apply -f replicaset.yml`

## Verificare i ReplicaSet lanciati

Per verificate i ReplicaSet lanciati nell'attuale namespace si utilizza il comando:

`kubectl get rs`

## Eliminare un ReplicaSet

Per eliminare un ReplicaSet si utilizza il comando:

`kubectl delete rs nome-del-replicaset`

> **Attenzione** Oltre ad eliminare il ReplicaSet verranno eliminati tutti i Pod ad esso associati

## Scalare un ReplicaSet

Per scalare il numero di repliche istanziate dal ReplicaSet si può procedere in due modalità:

* Aggiornare il template YAML e riapplicarlo mediante `kubectl apply`
* Editare il template *on the fly* mediante `kubectl edit`

In entrambi i casi si andrà a modificare la voce **replicas** specificando il numero di istance che si vuole ottenere.

La differenza tra i due sta solamente nella persistenza della modifica del template.
