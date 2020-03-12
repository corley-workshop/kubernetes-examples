# Esempio Docker

## Build immagine

Il comando `docker build` permette di buildare l'immagine del nostro applicativo, ad es.:

`docker build -t brisma/webapp_nodejs:1.0.0 .`

Verrà creata un'immagine di nome **brisma/webapp_nodejs** taggata con la versione **1.0.0**.

> **Attenzione** Il **.** finale che indica il contesto dov'è presente il **Dockerfile**.

## Login e Push su Docker Registry

Prima di poter effettuare il push di una immagine sul Docker Registry è necessario **autenticarsi** mediante il comando:

`docker login`

Infine, per pushare un'immagine, si utilizza il seguente comando:

`docker push brisma/webapp_nodejs:1.0.0`