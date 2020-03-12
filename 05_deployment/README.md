# Gestione Deployment

## Lanciare un Deployment nel cluster

Per lanciare il Deployment di questo esempio nel cluster possiamo utilizzare il comando:

`kubectl apply -f deployment.yml`

## Verificare i Deployment lanciati

Per verificate i Deployment lanciati nell'attuale namespace si utilizza il comando:

`kubectl get deploy`

## Eliminare un Deployment

Per eliminare un Deployment si utilizza il comando:

`kubectl delete deploy nome-del-deployment`

> **Attenzione** Oltre ad eliminare il Deployment verranno eliminati tutti i Pod/ReplicaSet ad esso associati **compresi** i volumi associati

## Aggiornare un Deployment

Per aggiornare un Deployment si possono utilizzare due modalità:
* Utilizzare il comando `set` della `kubectl`
* Utilizzare il comando `edit` della `kubectl`

### Aggiornare mediante il `set`

Esistono due modalità di utilizzo del **set**, ad esempio per cambiare l'immagine utilizzata si può scegliere tra:

`kubectl --record deployment.apps/nome-del-deployment set image deployment.v1.apps/nome-del-deployment nginx=nginx:1.9.1`

Oppure

`kubectl set image deployment/nome-del-deployment nginx=nginx:1.9.1 --record`

### Aggiornare mediate l'`edit`

Mediante il comando di `edit` è sempre possibile modificare il template del Deployment *on the fly*.

`kubectl edit deploy nome-del-deployment`

## Verificare lo stato del rollout

Quando si modifica un Deployment, in accordo alla strategia di deployment adottata, si può osservare come procede il processo di rollout con l'utilizzo del comando:

`kubectl rollout status deploy nome-del-deployment`

## Visualizzare lo storico dei rollout

Quando si modifica un Deployment e si registra l'operazione mediante l'uso del `record` viene salvata una fotografia del Deployment in quel momento. Per visualizzare tutte le mutazioni registrare si utilizza il comando:

`kubectl rollout history deploy nome-del-deployment`

Verrà visualizzata una lista di tutte le operazioni registrate, ad esempio:

```
REVISION  CHANGE-CAUSE
1         kubectl deployment.apps/nginx-deployment set image deployment.v1.apps/nginx-deployment nginx=nginx:1.9.0 --record=true
2         kubectl deployment.apps/nginx-deployment set image deployment.v1.apps/nginx-deployment nginx=nginx:1.9.1 --record=true
3         kubectl deployment.apps/nginx-deployment set image deployment.v1.apps/nginx-deployment nginx=nginx:1.9.2 --record=true
```

Volendo guardare nel dettaglio è possibile indicare la revisione nel comando history:

`kubectl rollout history deploy nome-del-deployment --revision numero-della-revision`

Che mostrerà ad esempio:

```
deployment.apps/nginx-deployment with revision #2
Pod Template:
  Labels:       app=nginx
        pod-template-hash=69fbc8b64f
  Annotations:  kubernetes.io/change-cause:
          kubectl deployment.apps/nginx-deployment set image deployment.v1.apps/nginx-deployment nginx=nginx:1.9.1 --record=true
  Containers:
   nginx:
    Image:      nginx:1.9.1
    Port:       80/TCP
    Host Port:  0/TCP
    Environment:        <none>
    Mounts:     <none>
  Volumes:      <none>
```

## Effettuare il rollback di un Deployment

Se si vuole effettuare il rollback di un Deployment alla precedente revisione di può utilizzare il comando:

`kubectl rollout undo deploy nome-del-deployment`

Mentre, se si vuole rollbackare ad una precisa revisione si utilizza il comando:

`kubectl rollout undo deploy nome-del-deployment --to-revision=numero-della-revision`

## Scalare un Deployment

Per scalare il numero di istanze di un Deployment è possibile utilizzare il comando:

`kubectl scale deploy nome-del-deployment --replicas numero-di-repliche`

## Sospendere e Ripristinare un Deployment

Durante un processo di rollout di un Deployment è possibile sospendere l'operazione al fine di effettuare nuove modifiche senza avere la necessità di completare il precedente rollout.

Infatti, mediante l'uso del comando:

`kubectl rollout pause deploy nome-del-deployment`

Verrà sospeso il rollout in corso (non verranno lanciate nuove istante).

Successivamente, dopo aver apportato le modifiche necessarie, è possibile riprendere il rollout (che terrà conto delle nuove modifiche) mediante l'utilizzo del comando:

`kubectl rollout resume deploy nome-del-deployment`