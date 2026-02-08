To start Kibana and Elastic search using docker:
On dev, make sure docker app is running :)
docker-compose up -d
To set the password:
In .env, define ELASTIC_PASSWORD

Kubernetes settings:
kubectl create secret generic elastic-secret \
  --from-literal=password='YourStrongPasswordHere'
kubectl apply -f elasticsearch-deployment.yaml
kubectl port-forward deployment/elasticsearch 9200:9200
curl -u elastic:YourStrongPasswordHere https://localhost:9200  (can do the test with thunder client)


Connect to elastic:
curl -u elastic:<PASSWORD> http://localhost:9200

Kibana address: http://localhost:5601

To check logs: docker logs es

To shut down, removing the volume (for a clean restart): docker-compose down -v

