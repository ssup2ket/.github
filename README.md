# ssup2ket

**ssup2ket** is an e-ecommerce toy project for personal study. ssup2ket aims to build as an **micro service architecture** based on **K8s** ([Kubernetes](https://kubernetes.io/)). ssup2ket services are deployed, operated, and monitored on K8s cluster. In addition, DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services also operate on K8s cluster.

ssup2ket project is composed of the following git repositories.

* [Auth service](https://github.com/ssup2ket/ssup2ket-auth-service) - Auth service git repository. Auth service manages user information and is responsible for authentication/authorization of ssup2ket service.

* [Store service](https://github.com/ssup2ket/ssup2ket-store-service) (WIP) - Store service git repostiroy. Ssup2ket Store service manages store and product inventory.

* Order service - Todo

* Payment service - Todo

* [Service deployment](https://github.com/ssup2ket/ssup2ket-service-deployment) - Service deployment configuration git repository for GitOps.

* [Helm charts](https://github.com/ssup2ket/ssup2ket-helm-charts) - Helm charts of DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services.

## ssup2ket Service Considerations

The following considerations are reflected in ssup2ket services.

* Service mesh - ssup2ket services use service mesh for detailed traffic control and easy monitoring. Service mesh is applied through [Istio](https://istio.io/). Istio uses [OpenTracing](https://opentracing.io/) for easy request tracing between multiple services.

* Event-driven architecture - ssup2ket service uses event-driven architecture for loose coupling and asynchronous processing. [Kafka](https://kafka.apache.org/) is used as the event of ssup2ket services.

* Transaction pattern - ssup2ket services use [saga pattern](https://microservices.io/patterns/data/saga.html) and [outbox pattern](https://microservices.io/patterns/data/transactional-outbox.html) for stable transaction processing.

* API - ssup2ket services supports HTTP and gRPC as APIs. HTTP API is provided for external clients, and gRPC API is provided for use between ssup2ket services. HTTP is defined through [OpenAPI 3.0](https://www.openapis.org/) and exposed through swagger.

* Log - ssup2ket services output the log in plain text format for easy debugging in a personal development environment, and output the log in JSON format for easy parsing when operating in K8s Cluster. Logs of ssup2ket services are collected by [Fluentd](https://www.fluentd.org/) and stored in [Elastic Search](https://www.elastic.co/elasticsearch/). All request related logs output TraceID based on OpenTracing to make it easy to trace the request.

* Metric - Metrics of ssup2ket services are collected through [Prometheus](https://prometheus.io/) and exporter, and visualized through [Grafana](https://grafana.com/).

* CI/CD - ssup2ket services use CI/CD for stable service distribution. CI (Continuous Integration) is performed through [Github Actions](https://github.com/features/actions) and CD (Continuous Deployment) is performed through [ArgoCD](https://argo-cd.readthedocs.io/en/stable/).

* Gracefully shutdown - Ssup2ket services supports gracefully shutdown to minimize deployment impact. K8s sends SIGTERM signal to notify the app of termination before the app termination. Therefore, when ssup2ket services receive a sigterm signal, they terminate the service gracefully.
