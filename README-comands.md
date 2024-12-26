# Ejemplos de comandos

## Para ver el cluster o todos los deployment

    kubectl get all

## Ejecutar los Archivos en secuencia
<!-- postgres-configMap - postgres-secret - postgres.yml(deployment) -->
<!-- pgadmin-secret - pg-admin -->

    kubectl apply -f nameFile.yml

## Para ver logs - primero asegúrate que el deployment este arriba

    kubectl get all
    kubectl logs nameDeployCorriendo (verifica posibles errores)
    kubectl describe nameDeployComplete (analiza)

<!-- en caso de algún error debes volver a aplicar los archivos en secuencia ln/8 -->

## Para Backend

    kubectl apply -f backend-secret.yml
    kubectl apply -f backend.yml
    kubectl get all
    kubectl describe nameDeployComplete
    kumectl logs nameDeployComplete
    kubectl rollout restart deployment

## Para limpieza de minukube

    minikube delete --all

## Pods

## Ver pods dentro de un "system"

    kubectl -n nameSystem get pods
    kubectl -n nameSystem get pods -o wide

<!-- =========================================== -->

## Imagen - crea imágenes a partir de un Dockerfile

    docker build -t nameImg/tagName

## Container - crea un contenedor a partir de una imagen

    docker container run `
    --name nameContainer `
    -e ENVNAME=valueEnv
    -d
    -p portLocal:portContainer
    nameImage:tagImage
