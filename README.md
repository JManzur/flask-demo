# Imagen demo Web flask

## Hacer build manual de la imagen
Desde el directorio que aloja el Dockerfile realizar:

```bash
docker build -t flask-demo-mp .
```
## Hacer push maul de la imagen ECR

Tagear la imagen que queremos subir, en este caso utilizo un generador de GUID para el tag

```bash
docker tags flask-demo-mps:latest URL_PERSONAL.ecr.us-east-1.amazonaws.com/prod/REGISTRY_NAME:GUID
```

Login en AWS:
```bash
aws configure
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin URL_PERSONAL.ecr.us-east-1.amazonaws.com/prod/REGISTRY_NAME
```

Push de la imagen:
```bash
docker push URL_PERSONAL.ecr.us-east-1.amazonaws.com/prod/REGISTRY_NAME:GUID
```