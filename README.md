## kubernetes-k8s-minikube-command

Get pods information - runner or workers
`kubectl get pods`


Create deployment (deploy name test-deploy) with replica set of 4. Allow to kill any pod and K8s recreate pod automatically
`kubectl scale deployment test-deploy --replicas 4`

Check replica set 
`kubectl get rs`

Create deployment (deploy name test-deploy)  with autoscale
`kubectl autoscale deployment test-deploy --min=2 --max=6 --cpu-percent=80`

Deploy history
`kubectl rollout history deployment/_test-deploy_`

Image update in deployment
``
