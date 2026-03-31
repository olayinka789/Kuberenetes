# generate pods manifest
kubectl run nginx --image=<IMAGE> --dry-run=client -o yaml > pod.yml

# generate deployment manifest
kubectl create deployment deployment/<NAME_DEPLOYMENT> --image=<IMAGE> --dry-run=client -o yaml > deployment.yml

# display the current-context
kubectl config current-context

# switch to the intended cluster
kubectl config use-context <CLUSTER_NAME>

# get extended information of the pods
kubectl get pods -o wide

# Show labels for all pods
kubectl get pods --show-labels

# Check rollout history
kubectl rollout history deployment <deployment-name>

# Undo the rollout
kubectl rollout undo deployment <deployment-name>

# expose kubernets svc for a named workspace
kubectl expose deployment <deployment-name> --port=80 --name=<service-name> -n <workspace-namespace>   