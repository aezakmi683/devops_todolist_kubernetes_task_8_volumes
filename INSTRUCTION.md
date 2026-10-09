# \# Validation

# 

# \## 1. Check the application

# 

# Verify that the Deployment and Pods are running in the `mateapp` namespace:

# 

# ```powershell

# kubectl get deployments -n mateapp

# kubectl get pods -n mateapp

# ```

# 

# \## 2. Check the PersistentVolume

# 

# Verify that the PersistentVolume exists and has the expected configuration:

# 

# ```powershell

# kubectl get pv

# kubectl describe pv

# ```

# 

# \## 3. Check the PersistentVolumeClaim

# 

# Verify that the PVC is bound:

# 

# ```powershell

# kubectl get pvc -n mateapp

# kubectl describe pvc -n mateapp

# ```

# 

# \## 4. Check the ConfigMap and mounted files

# 

# Verify the ConfigMap exists:

# 

# ```powershell

# kubectl get configmap -n mateapp

# kubectl describe configmap app-config -n mateapp

# ```

# 

# Verify that the application Pod mounts the ConfigMap at `/app/configs` as read-only:

# 

# ```powershell

# kubectl describe pods -n mateapp

# ```

# 

# Check the actual filenames mounted in `/app/configs` inside the application container:

# 

# ```powershell

# kubectl exec -n mateapp deployment/todoapp -- ls -la /app/configs

# ```

# 

# Verify the contents of each expected ConfigMap file using its actual filename:

# 

# ```powershell

# kubectl exec -n mateapp deployment/todoapp -- sh -c "for f in /app/configs/\*; do echo === $f; cat $f; done"

# ```

# 

# The filenames and contents under `/app/configs` should match the keys and values defined in the `app-config` ConfigMap.



