High Availability setup of Argo-CD: -

Argo CD is largely stateless. All data is persisted as Kubernetes objects, which in turn is stored in Kubernetes' etcd. Redis is only used as a throw-away cache and can be lost. When lost, it will be rebuilt without loss of service.

A set of HA manifests are need to setup for users who wish to run Argo CD in a highly available manner. This runs more containers, and runs Redis in HA mode.

NOTE: The HA installation will require at least three different nodes due to pod anti-affinity roles in the specs. Additionally, IPv6 only clusters are not supported.

https://argo-cd.readthedocs.io/en/stable/operator-manual/high_availability/