`brew install kubernetes-helm`


[11:36] 
`helm init`


[11:36] 
`helm install stable/prometheus`


[11:38] 
`export POD_NAME=$(kubectl get pods --namespace default -l "app=prometheus,component=server" -o jsonpath="{.items[0].metadata.name}")`
`kubectl --namespace default port-forward $POD_NAME 9090` (edited)


slackbot [11:43 AM] Only visible to you
Pssst! I didn’t unfurl https://github.com/nanit/tikal-hackathon because it was already shared in this channel quite recently (within the last hour) and I didn’t want to clutter things up.


Erez [11:43 AM] 
https://github.com/nanit/tikal-hackathon


boris [11:43 AM] 
helm install stable/grafana


[11:43] 
export POD_NAME=$(kubectl get pods --namespace default -l "app=fantastic-cow-grafana,component=grafana" -o jsonpath="{.items[0].metadata.name}")
     kubectl --namespace default port-forward $POD_NAME 3000


[11:46] 
kubectl get secret --namespace default fantastic-cow-grafana -o jsonpath="{.data.grafana-admin-password}" | base64 --decode ; echo


[11:46] 
fantastic-cow-grafana.default.svc.cluster.local


new messages
[11:47] 
vCNi9sjL21
