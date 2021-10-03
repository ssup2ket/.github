# Ssup2ket

**Ssup2ket** is an e-ecommerce toy project for personal study. ssup2ket aims to build as an **MSA** (Micro Service Architecture) based on **K8s** (Kubernetes). ssup2ket Service is deployed, operated, and monitored on K8s Cluster. In addition, DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services also operate on K8s Cluster.

Ssup2ket project is composed of the following git repositoryies.

* [Auth service](https://github.com/ssup2ket/ssup2ket-auth-service) : Auth service git repository. Auth service manages user information and is responsible for authentication/authorization of ssup2ket service.

* [Store service](https://github.com/ssup2ket/ssup2ket-store-service) : Store service git repostiroy. Ssup2ket Store service manages store and product inventory.

* Order service : Todo

* Payment service : Todo

* [Service deployment](https://github.com/ssup2ket/ssup2ket-service-deployment) : Service deployment configuration git repository for GitOps.

* [Helm charts](https://github.com/ssup2ket/ssup2ket-helm-charts) : Helm Chart of DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services.

## ssup2ket Service Considerations

### Service Mesh

### EDA (Event-driven Architecture)

### Transaction

### Logging

### CI/CD

### OpenAPI (Swagger)

### gRPC

### Gracefully Shutdown
