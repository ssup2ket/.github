# Ssup2ket

**Ssup2ket** is an e-ecommerce toy project for personal study. ssup2ket aims to build as an **micro service architecture** based on **K8s** (Kubernetes). ssup2ket services are deployed, operated, and monitored on K8s cluster. In addition, DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services also operate on K8s cluster.

Ssup2ket project is composed of the following git repositories.

* [Auth service](https://github.com/ssup2ket/ssup2ket-auth-service) - Auth service git repository. Auth service manages user information and is responsible for authentication/authorization of ssup2ket service.

* [Store service](https://github.com/ssup2ket/ssup2ket-store-service) - Store service git repostiroy. Ssup2ket Store service manages store and product inventory.

* Order service - Todo

* Payment service - Todo

* [Service deployment](https://github.com/ssup2ket/ssup2ket-service-deployment) - Service deployment configuration git repository for GitOps.

* [Helm charts](https://github.com/ssup2ket/ssup2ket-helm-charts) - Helm charts of DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services.

## Ssup2ket Service Considerations

The following considerations are reflected in ssup2ket services.

* Service mesh - Ssup2ket services use service mesh for detailed traffic control and easy monitoring. Service mesh is applied through [istio](https://istio.io/).

* Event-driven architecture - Ssup2ket service uses event-driven architecture for loose coupling and asynchronous processing. [Kafka](https://kafka.apache.org/) is used as the event of ssup2ket services.

* Transaction pattern - ssup2ket services use [saga pattern](https://microservices.io/patterns/data/saga.html) and [outbox pattern](https://microservices.io/patterns/data/transactional-outbox.html) for stable transaction processing.

* API - Ssup2ket services supports HTTP and gRPC as APIs. HTTP API is provided for external clients, and gRPC API is provided for use between ssup2ket services. HTTP is defined through [OpenAPI 3.0](https://www.openapis.org/) and exposed through Swagger.

* Logging - 

* Metric - 

* CI/CD - ssup2ket services use CI/CD for stable service distribution. CI (Continuous Integration) is performed through [Github Action](https://github.com/features/actions) and CD (Continuous Deployment) is performed through [ArgoCD](https://argo-cd.readthedocs.io/en/stable/).

* Gracefully shutdown - 
