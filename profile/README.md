# ssup2ket

**ssup2ket** is an e-ecommerce toy project for personal study. ssup2ket aims to build as an **micro service architecture** based on **K8s** ([Kubernetes](https://kubernetes.io/)). ssup2ket services are deployed, operated, and monitored on K8s cluster. In addition, DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services also operate on K8s cluster.

## Component Stack

ssup2ket project's component stack

![ssup2ket_component_stack](image/ssup2ket_component_stack.PNG)

## GIT Repositories

ssup2ket project is composed of the following git repositories.

* [Service auth](https://github.com/ssup2ket/service-auth) - Auth service git repository. Auth service manages user information and is responsible for authentication/authorization of ssup2ket service. Auth service is developed with **Golang**.

* [Service store](https://github.com/ssup2ket/service-store) - Store service git repostiroy. Ssup2ket Store service manages store and product inventory. Store service is developed with **Java on SpringBoot**.

* Service order - Todo

* Service payment - Todo

* Service web - Todo

* [Deploy services](https://github.com/ssup2ket/deploy-services) - Service deployment configuration git repository for GitOps.

* [Helm charts](https://github.com/ssup2ket/helm-charts) - Helm charts of DB, message queue, cache, proxy, log analyzer/collector, metric collector, and CI/CD tool used by ssup2ket services.

## ssup2ket Service Considerations

The following considerations are reflected in ssup2ket services.

* **Architecture** - Each ssup2ket service follows the [clean architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html). 

* **Service mesh** - ssup2ket services run on service mesh for detailed traffic control and easy monitoring. Service mesh is applied through [Istio](https://istio.io/). Istio uses [OpenTracing](https://opentracing.io/) for easy request tracing between multiple services.

* **Event-driven architecture** - ssup2ket services use event-driven architecture for loose coupling and asynchronous processing. [Kafka](https://kafka.apache.org/) is used as the event of ssup2ket services.

* **Transaction pattern** - ssup2ket services use [saga pattern](https://microservices.io/patterns/data/saga.html) and [outbox pattern](https://microservices.io/patterns/data/transactional-outbox.html) for stable transaction processing with [debezium outbox router](https://debezium.io/documentation/reference/1.8/transformations/outbox-event-router.html).

* **API** - ssup2ket services support **HTTP** and **gRPC** as APIs. HTTP API is provided for external clients, and gRPC API is provided for use between ssup2ket services. HTTP API is exposed through [OpenAPI 3.0](https://www.openapis.org/) and swagger. GRPC API supports reflection to discover services.

* **Healthz endpoint** - ssup2ket services supports the "/healthz" endpoint that can check the operating status of the service. The "/healthz" endpoint is used when configuring the liveness/readiness probe on K8s cluster.

* **Gracefully shutdown** - ssup2ket services supports gracefully shutdown to minimize deployment impact. K8s sends **SIGTERM** signal to notify the app of termination before the app termination. Therefore, when ssup2ket services receive a sigterm signal, they terminate the service gracefully.

* **Log** - ssup2ket services output the log in **plain text** format for easy debugging in a personal development environment, and output the log in **JSON** format for easy parsing when operating in K8s Cluster. Logs of ssup2ket services are collected by [Fluentd](https://www.fluentd.org/) and stored in [Elastic Search](https://www.elastic.co/elasticsearch/). All request related logs output TraceID based on OpenTracing to make it easy to trace the request.

* **Metric** - Metrics of ssup2ket services are collected through [Prometheus](https://prometheus.io/) and exporter, and visualized through [Grafana](https://grafana.com/).

* **CI/CD** - ssup2ket services use CI/CD for stable service distribution. CI (Continuous Integration) is performed through [Github Actions](https://github.com/features/actions) and CD (Continuous Deployment) is performed through [ArgoCD](https://argo-cd.readthedocs.io/en/stable/).
