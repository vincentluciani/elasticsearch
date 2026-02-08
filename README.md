To start Kibana and Elastic search:
On dev, make sure docker app is running :)
docker-compose up -d

To set the password:
In .env, define ELASTIC_PASSWORD

Connect to elastic:
curl -u elastic:<PASSWORD> http://localhost:9200

Kibana address: http://localhost:5601

To check logs: docker logs es

To shut down, removing the volume (for a clean restart): docker-compose down -v

