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

* Transaction pattern - 

* Logging - 

* Metric - 

* CI/CD - 

* Interface - 

* Gracefully shutdown - 
