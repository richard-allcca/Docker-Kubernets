# Ejemplos de comandos

## Para ver el cluster o todos los deployment

```bash
    kubectl get all
```

## Crear PODS o Servicios en el cluster

 Ejecutar los Archivos en secuencia

```bash
    kubectl apply -f postgres-configMap
    kubectl apply -f postgres-secret
    kubectl apply -f postgres.yml (deployment)

    # respetar la secuencia de comandos
    kubectl apply -f pgadmin-secret
    kubectl apply -f pg-admin
```

## Para ver logs

Primero asegúrate que el deployment este arriba

```bash
    kubectl get all

    # verifica posibles errores
    kubectl logs nameDeployCorriendo

    # analiza
    kubectl describe nameDeployComplete

    # en caso de algún error debes volver a aplicar los archivos en secuencia ln/8
```

## Exponer el servicio o imagen desplegada en el cluster

```bash
    minikube service nameDeploymentCorriendoQueQuieresExponer

    # Example - si el nombre la tiene 'service/' elimina esa parte
    minikube service service/pg-admin-service
    minikube service pg-admin-service
```

## Para Backend

```bash
    kubectl apply -f backend-secret.yml
    kubectl apply -f backend.yml
    kubectl get all
    kubectl describe nameDeployComplete
    kumectl logs nameDeployComplete
    kubectl rollout restart deployment
```

## Para limpieza de minukube

```bash
    minikube delete --all
```

## Pods

Ver pods dentro de un "system"

```bash
    kubectl -n nameSystem get pods
    kubectl -n nameSystem get pods -o wide
```

## Imagen - crea imágenes a partir de un Dockerfile

```bash
    docker build -t nameImg/tagName
```

## Container - crea un contenedor a partir de una imagen

```bash
    docker container run `
    --name nameContainer `
    -e ENVNAME=valueEnv `
    -d `
    -p portLocal:portContainer `
    nameImage:tagImage
```
