# Validation

## Check application

kubectl get deployments -n mateapp
kubectl get pods -n mateapp

## Check PV

kubectl get pv

## Check PVC

kubectl get pvc -n mateapp

## Check ConfigMap mount

kubectl exec -n mateapp <POD_NAME> -- ls /app/configs

## Check Secret mount

kubectl exec -n mateapp <POD_NAME> -- ls /app/secrets

## Check data volume

kubectl exec -n mateapp <POD_NAME> -- ls /app/data