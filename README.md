## kubernetes-k8s-minikube-command

Get pods information - runner or workers
```kubectl get pods```


Create deployment (deploy name test-deploy) with replica set of 4. Allow to kill any pod and K8s recreate pod automatically
`kubectl scale deployment test-deploy --replicas 4`

Check replica set 
`kubectl get rs`

Create deployment (deploy name test-deploy)  with autoscale
`kubectl autoscale deployment test-deploy --min=2 --max=6 --cpu-percent=80`

Deploy history
`kubectl rollout history deployment/test-deploy`

Deploy status and check after rollout any changes how your changes apply
`kubectl rollout status deployment/test-deploy`

Image update change in runned deployment (before need to know container name `kubectl describe deployment test-deploy` and check info next row after `Containers:` )
`kubectl set image deployment/test-deploy container-name=new-image-name:latest --record` 

Return deploy to 1 back in deploy history
`kubectl rollou undo deployment/test-deploy`

Return deploy to last 3 revision from deploy history
`kubectl rollou undo deployment/test-deploy --to-revision=4`

If new image version is always latest to update deployment
`kubectl rollout restart deployment/test-deploy`

Run Deployment manifest from CLI
`kubectl apply -f deployment-basic-manifest.yaml`

Check inside pod via port-forwarding to 777 from pods 80
`kubectl port-forward deploy-replica-pod-id 777:80`

Horizontal pod autoscaler check
`kubectl get hpa`

Remove Deployment from manifest CLI
`kubectl delete -f deployment-basic-manifest.yaml`

Delete all Deployments from manifest CLI
`kubectl delete deployment --all`


