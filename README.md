Procedure to start and test elastic search:
On dev, make sure docker app is running :)
kubectl create secret generic elastic-secret \
  --from-literal=password='YourStrongPasswordHere'
kubectl apply -f elasticsearch-deployment.yaml
kubectl port-forward deployment/elasticsearch 9200:9200
curl -u elastic:YourStrongPasswordHere https://localhost:9200  (can do the test with thunder client)


Connect to elastic using Thunder client:
Auth tab, basic sub-tab, enter elastic as user, and put the password set above.

Connection with curl:
curl -u elastic:'YourStrongPasswordHere' http://localhost:9200



