# route-table

This module creates following resources.

-   `aws_route_table`
-   `aws_route` (optional)
-   `aws_main_route_table_association` (optional)
-   `aws_route_table_association` (optional)
-   `aws_vpc_endpoint_route_table_association` (optional)
-   `aws_vpn_gateway_route_propagation` (optional)

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Requirements

| Name                                                                     | Version |
| ------------------------------------------------------------------------ | ------- |
| <a name="requirement_terraform"></a> [terraform](#requirement_terraform) | >= 0.15 |
| <a name="requirement_aws"></a> [aws](#requirement_aws)                   | >= 3.45 |

## Providers

| Name                                             | Version |
| ------------------------------------------------ | ------- |
| <a name="provider_aws"></a> [aws](#provider_aws) | 3.45.0  |

## Modules

No modules.

## Resources

| Name                                                                                                                                                              | Type     |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [aws_main_route_table_association.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/main_route_table_association)                 | resource |
| [aws_resourcegroups_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/resourcegroups_group)                                 | resource |
| [aws_route.ipv4](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route)                                                               | resource |
| [aws_route.ipv6](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route)                                                               | resource |
| [aws_route.prefix_list](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route)                                                        | resource |
| [aws_route_table.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route_table)                                                   | resource |
| [aws_route_table_association.gateways](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route_table_association)                       | resource |
| [aws_route_table_association.subnets](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route_table_association)                        | resource |
| [aws_vpc_endpoint_route_table_association.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_endpoint_route_table_association) | resource |
| [aws_vpn_gateway_route_propagation.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpn_gateway_route_propagation)               | resource |

## Inputs

| Name                                                                                                            | Description                                                                                                                                                                                    | Type                | Default                   | Required |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ------------------------- | :------: |
| <a name="input_name"></a> [name](#input_name)                                                                   | Desired name for the route table resources.                                                                                                                                                    | `string`            | n/a                       |   yes    |
| <a name="input_vpc_id"></a> [vpc_id](#input_vpc_id)                                                             | The ID of the VPC which the route table belongs to.                                                                                                                                            | `string`            | n/a                       |   yes    |
| <a name="input_gateways"></a> [gateways](#input_gateways)                                                       | A list of gateway IDs to associate with the route table. Only support Internet Gateway and Virtual Private Gateway.                                                                            | `list(string)`      | `[]`                      |    no    |
| <a name="input_ipv4_routes"></a> [ipv4_routes](#input_ipv4_routes)                                              | A list of route rules for IPv4 CIDRs.                                                                                                                                                          | `list(map(string))` | `[]`                      |    no    |
| <a name="input_ipv6_routes"></a> [ipv6_routes](#input_ipv6_routes)                                              | A list of route rules for IPv6 CIDRs.                                                                                                                                                          | `list(map(string))` | `[]`                      |    no    |
| <a name="input_is_main"></a> [is_main](#input_is_main)                                                          | Whether to set this route table as the main route table.                                                                                                                                       | `bool`              | `false`                   |    no    |
| <a name="input_module_tags_enabled"></a> [module_tags_enabled](#input_module_tags_enabled)                      | Whether to create AWS Resource Tags for the module informations.                                                                                                                               | `bool`              | `true`                    |    no    |
| <a name="input_prefix_list_routes"></a> [prefix_list_routes](#input_prefix_list_routes)                         | A list of route rules for Managed Prefix List.                                                                                                                                                 | `list(map(string))` | `[]`                      |    no    |
| <a name="input_propagating_vpn_gateways"></a> [propagating_vpn_gateways](#input_propagating_vpn_gateways)       | A list of Virtual Private Gateway IDs to propagate routes from.                                                                                                                                | `list(string)`      | `[]`                      |    no    |
| <a name="input_resource_group_description"></a> [resource_group_description](#input_resource_group_description) | The description of Resource Group.                                                                                                                                                             | `string`            | `"Managed by Terraform."` |    no    |
| <a name="input_resource_group_enabled"></a> [resource_group_enabled](#input_resource_group_enabled)             | Whether to create Resource Group to find and group AWS resources which are created by this module.                                                                                             | `bool`              | `true`                    |    no    |
| <a name="input_resource_group_name"></a> [resource_group_name](#input_resource_group_name)                      | The name of Resource Group. A Resource Group name can have a maximum of 127 characters, including letters, numbers, hyphens, dots, and underscores. The name cannot start with `AWS` or `aws`. | `string`            | `""`                      |    no    |
| <a name="input_subnets"></a> [subnets](#input_subnets)                                                          | A list of subnet IDs to associate with the route table.                                                                                                                                        | `list(string)`      | `[]`                      |    no    |
| <a name="input_tags"></a> [tags](#input_tags)                                                                   | A map of tags to add to all resources.                                                                                                                                                         | `map(string)`       | `{}`                      |    no    |
| <a name="input_vpc_gateway_endpoints"></a> [vpc_gateway_endpoints](#input_vpc_gateway_endpoints)                | A list of the VPC Endpoint IDs with which the Route Table will be associated.                                                                                                                  | `list(string)`      | `[]`                      |    no    |

## Outputs

| Name                                                                                                                                | Description                                                                      |
| ----------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| <a name="output_associated_gateways"></a> [associated_gateways](#output_associated_gateways)                                        | A list of gateway IDs which is associated with the route table.                  |
| <a name="output_associated_subnets"></a> [associated_subnets](#output_associated_subnets)                                           | A list of subnet IDs which is associated with the route table.                   |
| <a name="output_associated_vpc_gateway_endpoints"></a> [associated_vpc_gateway_endpoints](#output_associated_vpc_gateway_endpoints) | A list of the VPC Gateway Endpoint IDs which is associated with the route table. |
| <a name="output_id"></a> [id](#output_id)                                                                                           | The ID of the routing table.                                                     |
| <a name="output_is_main"></a> [is_main](#output_is_main)                                                                            | Whether to set this route table as the main route table.                         |
| <a name="output_propagated_vpn_gateways"></a> [propagated_vpn_gateways](#output_propagated_vpn_gateways)                            | A list of Virtual Private Gateway IDs which propagate routes from.               |
| <a name="output_vpc_id"></a> [vpc_id](#output_vpc_id)                                                                               | The ID of the VPC which the route table belongs to.                              |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
