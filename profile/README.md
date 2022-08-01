# uniframe.io

uniframe.io [(https://uniframe.io)](https://uniframe.io) is a String-Matching-as-a-Service product. It provides a ready-to-go string matching solution, and can be used in scenarios like data enrichment, KYC, data deduplication in data-intensive organisations. By using UniFrame, users can make string matching much easier and save a lot of time and effort. Below are the key features of UniFrame:

- A ready-to-go string matching product with user, data and task management
- Support both Web and Restful API interactive for business and developer. Can be easily integrated by Python, Excel and any other industry software.
- Accurate results on varied dataset, optimised algorithm to achieve efficient computation, highly customised configuration
- Data secured in all-round
- Can be hosted on your enterprise infrastructure

We open source the whole stack of uniframe.io, including:
- **uniframe-infra**: provisioning the AWS resources including networking (VPC, public and private subnet, NAT Gateway, router), route53, load balancers, RDS, S3, EKS and Helm charts setup on EKS.
- **uniframe-backend**: backend application. We use FastAPI as API server, sqlalchemy for ORM modeling, Kubernetes for computation and dynamic resource management.
- **uniframe-frontend**: frontend application by using Vue 3.
- **uniframe-docs**: documentation application by using Mkdocs. The documentation pages explain what is text matching, why needs text matching, and the manual of uniframe.io.
- **uniframe-minikube-deploy**: deploy the uniframe backend, frontend and documentation application on a local minikube environment.
- **uniframe-developer-example**: Python examples to interactive with uniframe backend.

## Installation
0. Prerequisite
    - Apply a AWS account, and set up AWS CLI
    - install AWS [CDK](https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html)

1. Provision AWS resources: 
    - navigate to uniframe-infra repository, and follow this [readme file](https://github.com/uniframe-io/uniframe-infra/blob/main/README.md#deploy-on-a-new-aws-account) to install AWS resources via AWS CDK. 
    - Then, run script `./scripts/helm-install-l2.sh` to install other components on EKS including Grafana, prometheus, aws load balancer controller, external DNS, Redis and other EKS plugins 
2. Backend application
    - Makefile [ci-test](https://github.com/uniframe-io/uniframe-backend/blob/main/Makefile#L8) runs some static testing, unit testing and integration testing.
    - Automatic deployment has been set up in Github Action [configuration](https://github.com/uniframe-io/uniframe-backend/tree/main/.github/workflows)
    - This [section](https://github.com/uniframe-io/uniframe-backend/blob/main/README.md#continue-deployment) has more explanation about back application deployment.
3. Frontend applicaiton: **TO BE FILLED**
4. Documentation application:
    - Run `make host-docs` to host documentation application manually
    - Automatic deployment has been set up in Github Action [configuration](https://github.com/uniframe-io/uniframe-docs/tree/main/.github/workflows)    

## License
All code published in this organization is subject to a Creative Commons Attribution-ShareAlike 4.0 ([CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)). **Please contact info@uniframe.io for any commercial usage**.