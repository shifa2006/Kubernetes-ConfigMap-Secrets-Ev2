# Kubernetes ConfigMaps and Secrets

## Project Overview
This project demonstrates how to use Kubernetes ConfigMaps and Secrets to manage application configuration and sensitive information.

## Objectives
- Create and manage ConfigMaps.
- Create and manage Secrets.
- Pass configuration through environment variables.
- Mount ConfigMaps as volumes.
- Mount Secrets as read-only volumes.
- Verify Kubernetes resources.

## Technologies Used
- Ubuntu
- Docker
- Kubernetes
- Kind
- kubectl
- YAML

## Implementation

### 1. Create ConfigMap
```bash
kubectl apply -f configmap.yaml
kubectl get configmap
```

### 2. Create Secret
```bash
kubectl apply -f secret.yaml
kubectl get secrets
```

Use your own local `secret.yaml` with actual values. Do not upload it to GitHub.

### 3. Create Pods
```bash
kubectl apply -f config-env-pod.yaml
kubectl apply -f config-volume-pod.yaml
kubectl apply -f secret-volume-pod.yaml
```

### 4. Verify Pods
```bash
kubectl get pods
```

### 5. Verify Environment Variables
```bash
kubectl exec config-env-demo -- printenv APP_NAME
kubectl exec config-env-demo -- printenv APP_ENV
```

### 6. Verify ConfigMap Volume
```bash
kubectl exec config-volume-demo -- ls /etc/app-config
```

### 7. Verify Secret Volume
```bash
kubectl exec secret-volume-demo -- ls /etc/app-secret
```

## Expected Results
- ConfigMap is created successfully.
- Secret is created successfully.
- All three Pods reach Running status.
- Configuration values are available through environment variables.
- ConfigMap and Secret are mounted inside their respective Pods.

## Conclusion
This project demonstrates Kubernetes ConfigMaps and Secrets using environment variables and volume mounting. It helps separate application configuration from container images and manage sensitive information more appropriately.

## Screenshots
Implementation screenshots are available in the `screenshots` folder.
