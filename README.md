# Cloud Operations Sandbox
This project aims primarily at demonstrating Cloud operations in a Site Reliability Engineering (SRE) fashion. But it actually comes with much more and may show case some other major Cloud Native aspects. Among these:
- the deployment a fully containerized micro-services based application, with a non-trivial merchant website
- lifecycle management and services exposition of a complex application through Kubernetes
- the deployment and use of a cluster-wide Istio service Mesh, offering many features related to traffic management and security
- the integration of various opensource projects related to observability (monitoring, logging, tracing, ...)
all this coming alongside the leveraging of a few Google Cloud key products like Google Kubernetes Engine and Networking services (e.g. external Load Balancer and Ingresses).

> Most of the stuff used here is originated from [GCP Cloud Ops sandbox GitHub project](https://github.com/GoogleCloudPlatform/cloud-ops-sandbox).

# Sandbox deployment
One can deploy part or all sandbox items using the steps of the `Deploy` stage of this project GitLab pipeline:

![alt text](img/pipeline-overview.PNG "Pipeline overview")

`1_create_cluster` job: deploy a full-blown GKE cluster  
`2_install_mesh`: deploy and configure Istio service mesh on the cluster, plus add-ons like Jaeger, Kiali, ...  
`3_deploy_hipster`: deploy the 10 micro-services running the demo webshop.

# Load generator setup
If needed, a load generator may be installed and made available through a UI.

To deploy the generator, run the `install_load_generator` out of the `sre_demo` stage in the pipeline. Pick the load generator public IP within the GitLab job logs, like here:

![alt text](img/load-generator-public-ip.PNG "Load generator Public IP")


# To be elaborated
- SRE demo and GCP Cloud operations scenarios
- GitOps (App + Infra)





