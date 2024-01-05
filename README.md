# my-elk-stack-chart
Elasticsearch and Kibana deployment
## Deploying ElasticSearch and Kibana
cd my-elk-stack-chart\my-elk-stack-chart\templates
kubectl apply -f elasticsearch-deployment.yaml
kubectl apply -f elasticsearch-service.yaml
kubectl apply -f kibana-deployment.yaml
kubectl apply -f kibana-service.yaml


kubectl apply -f elasticsearch-snapshot-repository.yaml
kubectl apply -f elasticsearch-slm-policy.yaml
Elasticsearch Snapshot Lifecycle Management (SLM) policy named daily-backups scheduled to run daily at 2:00 AM. This policy is configured to create daily snapshots of all indices, storing them in a repository named my-repository. The snapshots are retained for 7 days, with a minimum count of 5 and a maximum count of 20. This ensures a daily backup routine with a dynamic date-based snapshot naming convention, facilitating easy identification and management.


