# Minikube

Minikube permette l'avvio di un cluster locale di Kubernetes in pochi passi.

## Installazione Minikube

Fare riferimento al seguente link:
https://minikube.sigs.k8s.io/docs/start/

## Avviare un cluster

Per avviare un cluster si utilizza il comando:

`minikube start`

Verranno scaricati tutti i componenti necessari all'avvio del cluster locale di Kubernetes.

## Indirizzo IP del cluster

Per ottenere l'indirizzo IP del cluster si utilizza il comando:

`minikube ip`

## Avviare la Dashboard

Per avviare la Dashboard grafica di minikube si utilizza il comando:

`minikube dashboard`

> **Attenzione** Se si interrompe il processo la dashboard non sarà più disponibile

## Fermare il cluster

Per fermare il cluster si può utilizzare il comando:

`minikube stop`

## Eliminare il cluster

Per eliminare il cluster si può utilizzare il comando:

`minikube delete`

## Loggarsi nel cluster

Per loggarsi in **ssh** all'interno del cluster si può utilizzare il comando:

`minikube ssh`

## Utilizzare Kubectl

Se non si ha installata la kubectl localmente è possibile utilizzare quella integrata in minikube mediante il comando:

`minikube kubectl ...`
