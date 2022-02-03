# vpc-endpoint-service

This module creates following resources.

-   `aws_vpc_endpoint_service`
-   `aws_vpc_endpoint_service_allowed_principal` (optional)
-   `aws_vpc_endpoint_connection_notification` (optional)

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Requirements

| Name                                                                     | Version |
| ------------------------------------------------------------------------ | ------- |
| <a name="requirement_terraform"></a> [terraform](#requirement_terraform) | >= 0.15 |
| <a name="requirement_aws"></a> [aws](#requirement_aws)                   | >= 3.45 |

## Providers

| Name                                             | Version |
| ------------------------------------------------ | ------- |
| <a name="provider_aws"></a> [aws](#provider_aws) | 3.50.0  |

## Modules

No modules.

## Resources

| Name                                                                                                                                                                  | Type     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [aws_resourcegroups_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/resourcegroups_group)                                     | resource |
| [aws_vpc_endpoint_connection_notification.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_endpoint_connection_notification)     | resource |
| [aws_vpc_endpoint_service.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_endpoint_service)                                     | resource |
| [aws_vpc_endpoint_service_allowed_principal.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_endpoint_service_allowed_principal) | resource |

## Inputs

| Name                                                                                                               | Description                                                                                                                                                                                    | Type                                                                            | Default                   | Required |
| ------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------- | :------: |
| <a name="input_name"></a> [name](#input_name)                                                                      | Desired name for the VPC Endpoint Service.                                                                                                                                                     | `string`                                                                        | n/a                       |   yes    |
| <a name="input_acceptance_required"></a> [acceptance_required](#input_acceptance_required)                         | Whether or not VPC endpoint connection requests to the service must be accepted by the service owner.                                                                                          | `bool`                                                                          | `false`                   |    no    |
| <a name="input_allowed_principals"></a> [allowed_principals](#input_allowed_principals)                            | A list of the ARNs of principal to allow to discover a VPC endpoint service.                                                                                                                   | `list(string)`                                                                  | `[]`                      |    no    |
| <a name="input_gateway_load_balancer_arns"></a> [gateway_load_balancer_arns](#input_gateway_load_balancer_arns)    | List of Amazon Resource Names of one or more Gateway Load Balancers for the endpoint service.                                                                                                  | `list(string)`                                                                  | `null`                    |    no    |
| <a name="input_module_tags_enabled"></a> [module_tags_enabled](#input_module_tags_enabled)                         | Whether to create AWS Resource Tags for the module informations.                                                                                                                               | `bool`                                                                          | `true`                    |    no    |
| <a name="input_network_load_balancer_arns"></a> [network_load_balancer_arns](#input_network_load_balancer_arns)    | List of Amazon Resource Names of one or more Network Load Balancers for the endpoint service.                                                                                                  | `list(string)`                                                                  | `null`                    |    no    |
| <a name="input_notification_configurations"></a> [notification_configurations](#input_notification_configurations) | A list of configurations of Endpoint Connection Notifications for VPC Endpoint events.                                                                                                         | <pre>list(object({<br> sns_arn = string<br> events = list(string)<br> }))</pre> | `[]`                      |    no    |
| <a name="input_private_domain"></a> [private_domain](#input_private_domain)                                        | The private domain name for the service.                                                                                                                                                       | `string`                                                                        | `null`                    |    no    |
| <a name="input_resource_group_description"></a> [resource_group_description](#input_resource_group_description)    | The description of Resource Group.                                                                                                                                                             | `string`                                                                        | `"Managed by Terraform."` |    no    |
| <a name="input_resource_group_enabled"></a> [resource_group_enabled](#input_resource_group_enabled)                | Whether to create Resource Group to find and group AWS resources which are created by this module.                                                                                             | `bool`                                                                          | `true`                    |    no    |
| <a name="input_resource_group_name"></a> [resource_group_name](#input_resource_group_name)                         | The name of Resource Group. A Resource Group name can have a maximum of 127 characters, including letters, numbers, hyphens, dots, and underscores. The name cannot start with `AWS` or `aws`. | `string`                                                                        | `""`                      |    no    |
| <a name="input_tags"></a> [tags](#input_tags)                                                                      | A map of tags to add to all resources.                                                                                                                                                         | `map(string)`                                                                   | `{}`                      |    no    |

## Outputs

| Name                                                                                                                       | Description                                                                                       |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| <a name="output_allowed_principals"></a> [allowed_principals](#output_allowed_principals)                                  | A list of the ARNs of allowed principals to discover a VPC endpoint service.                      |
| <a name="output_arn"></a> [arn](#output_arn)                                                                               | The Amazon Resource Name (ARN) of the VPC endpoint service.                                       |
| <a name="output_availability_zones"></a> [availability_zones](#output_availability_zones)                                  | The Availability Zones in which the service is available.                                         |
| <a name="output_base_domain_names"></a> [base_domain_names](#output_base_domain_names)                                     | The DNS names for the service.                                                                    |
| <a name="output_gateway_load_balancer_arns"></a> [gateway_load_balancer_arns](#output_gateway_load_balancer_arns)          | ARNs of Gateway Load Balancers which is associated to the endpoint service.                       |
| <a name="output_id"></a> [id](#output_id)                                                                                  | The ID of the VPC endpoint service.                                                               |
| <a name="output_manages_vpc_endpoints"></a> [manages_vpc_endpoints](#output_manages_vpc_endpoints)                         | Whether or not the service manages its VPC endpoints                                              |
| <a name="output_name"></a> [name](#output_name)                                                                            | The VPC Endpoint Service name.                                                                    |
| <a name="output_network_load_balancer_arns"></a> [network_load_balancer_arns](#output_network_load_balancer_arns)          | ARNs of Network Load Balancers which is associated to the endpoint service.                       |
| <a name="output_notification_configurations"></a> [notification_configurations](#output_notification_configurations)       | A list of Endpoint Connection Notifications for VPC Endpoint events.                              |
| <a name="output_private_domain"></a> [private_domain](#output_private_domain)                                              | The private DNS name for the service.                                                             |
| <a name="output_private_domain_configurations"></a> [private_domain_configurations](#output_private_domain_configurations) | List of objects containing information about the endpoint service private DNS name configuration. |
| <a name="output_service_name"></a> [service_name](#output_service_name)                                                    | The service name.                                                                                 |
| <a name="output_service_type"></a> [service_type](#output_service_type)                                                    | The service type, `Gateway` or `Interface`.                                                       |
| <a name="output_state"></a> [state](#output_state)                                                                         | The state of the VPC endpoint service.                                                            |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
