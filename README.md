<!--- app-name: PostgreSQL HA -->

# PostgreSQL HA packaged by Bitnami - Modified  for purpose

Bitnami Postgresql-ha Helm chart - modified for our use case. Do refer the actual helm chart 11.7.7 [here](https://artifacthub.io/packages/helm/bitnami/postgresql-ha/11.7.7), and refer [githu](https://github.com/bitnami/charts/tree/main/bitnami/postgresql-ha) for Readme on details about what postgres-ha is about.

## Backdrop
We love container orchestration and we use Kubernetes for deploying our services. We have been running single k8 pod running postgresql 11.X until now, but due to large amount of data being read/written to it, performance started taking hit.  I'm privileged to be where I'm now I guess, with freedom to try out different tools/technologies. We're small team, still on constant learning journey so trying things we can adopt quickly. I learnt bit about Helm charts and really like the way it helps in deploying services, somewhat similar to what docker-compose is for docker based deployments. 

Next came learning Bitnami Postgresql-ha deployment as we want to have cluster with 1 primary and 2 standby pods (default recommended). We have underlying S3 storage on top of which we create the required PVC.

For username, password etc we can use k8 secrets, but for now its not required, so you can try that based on your usecase.
### Bring the cluster up.

To bring up the helm chart, you can use following command

    helm install my-pg-cluster -n postgres-cluster ./postgresql-ha

boom, that brings up nicely runing postgres cluster. Feel free to ask any  questions, I'll try to reply as soon as I can. We