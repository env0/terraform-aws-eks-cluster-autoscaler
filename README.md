# AWS EKS cluster autoscaler Terraform module

[![labyrinth labs logo](ll-logo.png)](https://lablabs.io/)

We help companies build, run, deploy and scale software and infrastructure by embracing the right technologies and principles. Check out our website at https://lablabs.io/

---

![Terraform validation](https://github.com/lablabs/terraform-aws-eks-node-problem-detector/workflows/Terraform%20validation/badge.svg?branch=master)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-success?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

## Description

A terraform module to deploy the Cluster Autoscaler on Amazon EKS cluster.

## Related Projects

Check out these related projects.

- [terraform-aws-eks-external-dns](https://github.com/lablabs/terraform-aws-eks-external-dns)
- [terraform-aws-eks-calico](https://github.com/lablabs/terraform-aws-eks-calico)
- [terraform-aws-eks-alb-ingress](https://github.com/lablabs/terraform-aws-eks-alb-ingress)
- [terraform-aws-eks-metrics-server](https://github.com/lablabs/terraform-aws-eks-metrics-server)
- [terraform-aws-eks-prometheus-node-exporter](https://github.com/lablabs/terraform-aws-eks-prometheus-node-exporter)
- [terraform-aws-eks-kube-state-metrics](https://github.com/lablabs/terraform-aws-eks-kube-state-metrics)
- [terraform-aws-eks-node-problem-detector](https://github.com/lablabs/terraform-aws-eks-node-problem-detector)


## Examples

See [Basic example](examples/basic/README.md) for further information.
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.13 |
| aws | >= 2.0 |
| helm | >= 1.0 |
| kubernetes | >= 1.10 |

## Modules

No Modules.

## Resources

| Name |
|------|
| [aws_iam_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_policy) |
| [aws_iam_policy_document](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) |
| [aws_iam_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) |
| [aws_iam_role_policy_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) |
| [aws_region](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/region) |
| [helm_release](https://registry.terraform.io/providers/hashicorp/helm/latest/docs/resources/release) |
| [kubernetes_namespace](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/namespace) |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| cluster\_identity\_oidc\_issuer | The OIDC Identity issuer for the cluster | `string` | n/a | yes |
| cluster\_identity\_oidc\_issuer\_arn | The OIDC Identity issuer ARN for the cluster that can be used to associate IAM roles with a service account | `string` | n/a | yes |
| cluster\_name | The name of the cluster | `string` | n/a | yes |
| enabled | Variable indicating whether deployment is enabled | `bool` | `true` | no |
| helm\_chart\_name | Helm chart name to be installed | `string` | `"cluster-autoscaler"` | no |
| helm\_chart\_version | Version of the Helm chart | `string` | `"9.7.0"` | no |
| helm\_release\_name | Helm release name | `string` | `"cluster-autoscaler"` | no |
| helm\_repo\_url | Helm repository | `string` | `"https://kubernetes.github.io/autoscaler"` | no |
| k8s\_namespace | The K8s namespace in which the node-problem-detector service account has been created | `string` | `"cluster-autoscaler"` | no |
| k8s\_service\_account\_name | The k8s cluster-autoscaler service account name | `string` | `"cluster-autoscaler"` | no |
| mod\_dependency | Dependence variable binds all AWS resources allocated by this module, dependent modules reference this variable | `bool` | `null` | no |
| settings | Additional settings which will be passed to the Helm chart values, see https://hub.helm.sh/charts/stable/cluster-autoscaler | `map(any)` | `{}` | no |
| values | Additional yaml encoded values which will be passed to the Helm chart, see https://hub.helm.sh/charts/stable/cluster-autoscaler | `string` | `""` | no |

## Outputs

No output.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Contributing and reporting issues

Feel free to create an issue in this repository if you have questions, suggestions or feature requests.

### Validation, linters and pull-requests

We want to provide high quality code and modules. For this reason we are using
several [pre-commit hooks](.pre-commit-config.yaml) and
[GitHub Actions workflow](.github/workflows/main.yml). A pull-request to the
master branch will trigger these validations and lints automatically. Please
check your code before you will create pull-requests. See
[pre-commit documentation](https://pre-commit.com/) and
[GitHub Actions documentation](https://docs.github.com/en/actions) for further
details.


## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

See [LICENSE](LICENSE) for full details.

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.
