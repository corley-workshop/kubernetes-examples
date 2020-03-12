# Gestione StatefulSet

## Lanciare un StatefulSet nel cluster

Per lanciare il StatefulSet di questo esempio nel cluster possiamo utilizzare il comando:

`kubectl apply -f statefulset.yml`

## Verificare i StatefulSet lanciati

Per verificate i StatefulSet lanciati nell'attuale namespace si utilizza il comando:

`kubectl get statefulset`

## Eliminare un StatefulSet

Per eliminare un StatefulSet si utilizza il comando:

`kubectl delete statefulset nome-del-statefulset`

> **Attenzione** Oltre ad eliminare il StatefulSet verranno eliminati tutti i Pod/ReplicaSet ad esso associati ma **non** i volumi associati

## Visualizzare i PersistentVolume
Per visualizzare i PersistentVolume si utilizza il comando:

`kubectl get pv`

## Visualizzare i PersistentVolumeClaim
Per visualizzare i PersistentVolumeClaim si utilizza il comando:

`kubectl get pvc`
