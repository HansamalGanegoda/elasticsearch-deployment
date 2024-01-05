# my-elk-stack-chart

## Elasticsearch and Kibana Deployment

This Helm chart deploys Elasticsearch and Kibana for your ELK stack.

### Deploying ElasticSearch and Kibana
### Elasticsearch Snapshot Lifecycle Management (SLM)
An SLM policy named daily-backups is scheduled to run daily at 2:00 AM. This policy creates daily snapshots of all indices, storing them in a repository named my-repository. The snapshots are retained for 7 days, with a minimum count of 5 and a maximum count of 20. This ensures a daily backup routine with a dynamic date-based snapshot naming convention, facilitating easy identification and management.

Navigate to the chart's templates directory:

cd my-elk-stack-chart/my-elk-stack-chart/templates
Deploy Elasticsearch:

kubectl apply -f elasticsearch-deployment.yaml
kubectl apply -f elasticsearch-service.yaml

Deploy Kibana:

kubectl apply -f kibana-deployment.yaml
kubectl apply -f kibana-service.yaml

set up Elasticsearch Snapshot Repository and SLM policy:

kubectl apply -f elasticsearch-snapshot-repository.yaml
kubectl apply -f elasticsearch-slm-policy.yaml

