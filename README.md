
kind: ReplicationController
`
# get node where kubectl is running
kubectl get node
# Create config architecture using a yml file
kubectl create -f fichier.yml
# Show all available pod
kubectl get pods
# Describe this pod
kubectl describe pod helloworld-controller-sczzz
# delete one pod
kubectl delete pod helloworld-controller-sczzz
# Scaling with 4 replicas using yml file
kubectl scale --replicas=4 -f fichier.yml
# Scaling with 1 replica using replication controller command
kubectl scale --replicas=1 rc/helloworld-controller
`

kind: Deployment uses Replication Set (advanced feature of ReplicationController)
`
# Get information on current deployments
kubectl get deployments
# Get information about replica sets
kubectl get rs
# Get pods, and also show labels attached to those pods
kubectl get pods --show-labels
# Get deployment status
kubectl rollout status deployment/helloworld-deployment
# Expose app
kubectl expose deployment helloworld-deployment --type=NodePort
# See current services
kubectl get service
# Describe service to see the node port
kubectl describe service helloworld-deployment
# Run k8s-demo with the image label version 2
kubectl set image deployment/helloworld-deployment k8s-demo=wardviaene/k8s-demo:2
# Get the status of the rollout
kubectl rollout status deployment/helloworld-deployment
# Get the rollout history
kubectl rollout history deployment/helloworld-deployment
# Rollback to previous version
kubectl rollout undo deployment/helloworld-deployment
# Rollback to revision number
kubectl rollout undo deployment/helloworld-deployment --to-revision=3
`