# Gestione DaemonSet

## Lanciare un DaemonSet nel cluster

Per lanciare il DaemonSet di questo esempio nel cluster possiamo utilizzare il comando:

`kubectl apply -f daemonset.yml`

## Verificare i DaemonSet lanciati

Per verificate i DaemonSet lanciati nell'attuale namespace si utilizza il comando:

`kubectl get daemonset`

## Eliminare un DaemonSet

Per eliminare un DaemonSet si utilizza il comando:

`kubectl delete daemonset nome-del-daemonset`
