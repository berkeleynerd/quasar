
---
title: "Documentation"
linkTitle: "Documentation"
weight: 20
menu:
  main:
    weight: 20
---

# Table of contents

* [Introduction](gb-readme.md)

## Dev Environment

* [Command line tools](dev-environment/cli.md)
* [Go](dev-environment/go.md)
* [Goland](core-concepts-and-technologies/goland.md)
* [Git and Github](core-concepts-and-technologies/git-and-github.md)

## Fundamentals

* [Contents](fundamentals/toc.md)
* [Testing](fundamentals/tdd.md)
* [Workflow](fundamentals/workflow.md)
* [Hello, World](fundamentals/hello-world.md)
* [Integers](fundamentals/integers.md)
* [Iteration](fundamentals/iteration.md)
* [Arrays and slices](fundamentals/arrays-and-slices.md)
* [Structs, methods, and interfaces](fundamentals/structs-methods-and-interfaces.md)
* [Pointers and errors](fundamentals/pointers-and-errors.md)
* [Maps](fundamentals/maps.md)
* [Dependency Injection](fundamentals/dependency-injection.md)
* [Mocking](fundamentals/mocking.md)
* [Concurrency](fundamentals/concurrency.md)
* [Select](fundamentals/select.md)
* [Reflection](fundamentals/reflection.md)
* [Sync](fundamentals/sync.md)
* [Context](fundamentals/context.md)
* [Property based tests](fundamentals/roman-numerals.md)
* [Math](fundamentals/math.md)
* [File I/O](fundamentals/reading-files.md)

## Build a service

* [Local Development](build-a-service/local-development/README.md)
  * [Git-forking workflow](build-a-service/local-development/git-forking-workflow.md)
  * [Eve service template](build-a-service/local-development/http-server.md)
  * [Local development](build-a-service/local-development/app-intro.md)
  * [Create a request](build-a-service/local-development/create-a-request.md)
  * [Create a new event](build-a-service/local-development/create-a-new-event.md)
  * [Send an event](build-a-service/local-development/send-an-event.md)
  * [Receive an event](build-a-service/local-development/receive-an-event.md)
  * [Working with the Monolith](build-a-service/local-development/working-with-the-monolith.md)
* [Quasar Services](build-a-service/quasar-services/README.md)
  * [Stateless vs Stateful](build-a-service/quasar-services/stateless-vs-stateful.md)
  * [Microservices](build-a-service/quasar-services/microservices.md)
  * [Domain Services](build-a-service/quasar-services/domain-services.md)
  * [Domain Driven Design](build-a-service/quasar-services/domain-driven-design/README.md)
    * [Bounded Context](build-a-service/quasar-services/domain-driven-design/bounded-context.md)
    * [Authoritative Context](build-a-service/quasar-services/domain-driven-design/authoritative-context.md)
    * [Tenancy](build-a-service/quasar-services/domain-driven-design/tenancy.md)
    * [Event Sourcing](build-a-service/quasar-services/domain-driven-design/event-sourcing.md)
    * [CQRS](build-a-service/quasar-services/domain-driven-design/cqrs.md)
  * [The 12 Factor App](build-a-service/quasar-services/the-12-factor-app.md)
* [Containers](build-a-service/containers/README.md)
  * [Docker](build-a-service/containers/docker.md)
  * [Docker Compose](build-a-service/containers/docker-compose.md)
  * [Container Registries](build-a-service/containers/container-registries.md)
* [Messaging](build-a-service/json/README.md)
  * [The monolith](build-a-service/json/the-monolith.md)
  * [Message bus](build-a-service/json/message-bus.md)
  * [Public gateway](build-a-service/json/public-gateway.md)
  * [Service gateway](build-a-service/json/service-gateway.md)
  * [Protobuf](build-a-service/json/protobuf.md)
  * [gRPC](build-a-service/json/grpc.md)
  * [Quasar Primitives](build-a-service/json/quasar-primitives/README.md)
    * [Events](build-a-service/json/quasar-primitives/events.md)
    * [Requests](build-a-service/json/quasar-primitives/requests.md)
    * [Notices](build-a-service/json/quasar-primitives/notices.md)

## Deploy a service

* [Deploy a service](deploy-a-service/deploy-a-service.md)

***

* [Logging and Tracing](logging-and-tracing/README.md)
* [Deploying](deploying/README.md)
  * [Create a new project](deploying/create-a-new-project.md)
  * [Kubernetes](deploying/kubernetes/README.md)
    * [Pods](deploying/kubernetes/pods.md)
    * [Nodes](deploying/kubernetes/nodes.md)
    * [Deployments](deploying/kubernetes/deployments.md)
    * [Services](deploying/kubernetes/services.md)
    * [Replicasets](deploying/kubernetes/replicasets.md)
    * [Statefulsets](deploying/kubernetes/statefulsets.md)
    * [Persistant Volumes](deploying/kubernetes/persistant-volumes.md)
  * [Dev, test, and live](deploying/dev-test-and-live.md)
  * [Prometheus](deploying/prometheus.md)
  * [Grafana](deploying/grafana.md)
  * [Sentry](logging-and-tracing/sentry.md)
  * [Honeycomb](logging-and-tracing/honeycomb.md)
  * [Vault](deploying/vault.md)
  * [Terraform](deploying/terraform.md)
* [Deploy a service](deploy-a-service-1.md)

## Topics

* [PostgreSQL](topics/postgresql.md)
* [Redis](topics/topics.md)

***

* [FAQ](faq.md)

## Scratch

* [Snippets](scratch/snippets.md)
