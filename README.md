# kustomize-sandbox

## DEVELOPMENT
### build (Docker image)

```
docker build -t keyno63/kostmize-sample:v1 .
```

### deploy
- dev
```
kustomize build manifests/overlays/dev | kubectl apply -f 
```
- prod
```
kustomize build manifests/overlays/prod | kubectl apply -f 
```

## LISENCE

Licensed under the [LISENCE](./LISENCE)