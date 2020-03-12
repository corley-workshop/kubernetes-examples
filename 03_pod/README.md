# Gestione Pod

## Lanciare un Pod nel cluster

Per lanciare il Pod di questo esempio nel cluster possiamo utilizzare il comando:

`kubectl apply -f pod.yml`

## Verificare i Pod lanciati

Per verificate i Pod lanciati nell'attuale namespace si utilizza il comando:

`kubectl get pods`

## Ottenere informazioni su un Pod

Si può ottenere tutte le informazioni di un Pod mediante il comando:

`kubectl describe pods nome-del-pod`

Verranno riportate molte informazioni come ad esempio il Nodo su cui è stato avviato, l'indirizzo IP che ha ottenuto, lo stato dei suoi container etc.

## Lanciare comandi in un Pod

Per lanciare un singolo processo all'interno di un Pod si utilizza il comando:

`kubectl exec nome-del-pod comando`

## Entrare in un Pod

Per interagire direttamente all'interno di un Pod si può utilizzare il comando:

`kubectl exec -it myapp-pod sh/ash/dash/bash/zsh`

Verrà avviata una bash interattiva nel Pod di nome **myapp-pod**.

## Eliminare un Pod

Per eliminare un Pod si utilizza il comando:

`kubectl delete pods nome-del-pod`

> **Attenzione** Se il Pod è stato avviato da un Controller (ad es. un ReplicaSet) esso verrà ricostruito.

## Ottenere i log di un Pod

Per visualizzare i log di un Pod si utilizza il comando:

`kubectl logs nome-del-pod`

## Editare il template di un Pod

Una particolare funzionalità non molto citata della **kubectl** è la possibilità di modificare il template di un Pod *on the fly* utilizzando il comando:

`kubectl edit pods nome-del-pod`

## Esporre una porta solo su host

Si può esporre una porta sull'host utilizzando il comando:

`kubectl port-forward nome-del-pod porta-host:porta-container`
