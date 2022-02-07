# nat-gateway

This module creates following resources.

-   `aws_nat_gateway`
-   `aws_eip` (optional)

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

| Name                                                                                                                              | Type     |
| --------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [aws_eip.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eip)                                   | resource |
| [aws_nat_gateway.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/nat_gateway)                   | resource |
| [aws_resourcegroups_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/resourcegroups_group) | resource |

## Inputs

| Name                                                                                                            | Description                                                                                                                                                                                    | Type          | Default                   | Required |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------------------- | :------: |
| <a name="input_name"></a> [name](#input_name)                                                                   | Desired name for the NAT Gateway resources.                                                                                                                                                    | `string`      | n/a                       |   yes    |
| <a name="input_subnet_id"></a> [subnet_id](#input_subnet_id)                                                    | The ID of the subnet which the NAT Gateway belongs to.                                                                                                                                         | `string`      | n/a                       |   yes    |
| <a name="input_assign_eip_on_create"></a> [assign_eip_on_create](#input_assign_eip_on_create)                   | Assign a new Elastic IP to NAT Gateway on create. Set false if you want to provide existing Elastic IP.                                                                                        | `bool`        | `false`                   |    no    |
| <a name="input_eip_id"></a> [eip_id](#input_eip_id)                                                             | The Allocation ID of the Elastic IP address for the gateway. Create a new Elastic IP if not provided.                                                                                          | `string`      | `""`                      |    no    |
| <a name="input_is_private"></a> [is_private](#input_is_private)                                                 | Whether to create the gateway as private or public connectivity type. Defaults to public(false).                                                                                               | `bool`        | `false`                   |    no    |
| <a name="input_module_tags_enabled"></a> [module_tags_enabled](#input_module_tags_enabled)                      | Whether to create AWS Resource Tags for the module informations.                                                                                                                               | `bool`        | `true`                    |    no    |
| <a name="input_resource_group_description"></a> [resource_group_description](#input_resource_group_description) | The description of Resource Group.                                                                                                                                                             | `string`      | `"Managed by Terraform."` |    no    |
| <a name="input_resource_group_enabled"></a> [resource_group_enabled](#input_resource_group_enabled)             | Whether to create Resource Group to find and group AWS resources which are created by this module.                                                                                             | `bool`        | `true`                    |    no    |
| <a name="input_resource_group_name"></a> [resource_group_name](#input_resource_group_name)                      | The name of Resource Group. A Resource Group name can have a maximum of 127 characters, including letters, numbers, hyphens, dots, and underscores. The name cannot start with `AWS` or `aws`. | `string`      | `""`                      |    no    |
| <a name="input_tags"></a> [tags](#input_tags)                                                                   | A map of tags to add to all resources.                                                                                                                                                         | `map(string)` | `{}`                      |    no    |

## Outputs

| Name                                                                                   | Description                                                             |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| <a name="output_connectivity_type"></a> [connectivity_type](#output_connectivity_type) | Connectivity type for the gateway. Valid values are private and public. |
| <a name="output_eip_id"></a> [eip_id](#output_eip_id)                                  | The Allocation ID of the Elastic IP address for the gateway.            |
| <a name="output_eni_id"></a> [eni_id](#output_eni_id)                                  | The ENI ID of the network interface created by the NAT gateway.         |
| <a name="output_id"></a> [id](#output_id)                                              | The ID of the NAT Gateway.                                              |
| <a name="output_private_ip"></a> [private_ip](#output_private_ip)                      | The private IP address of the NAT Gateway.                              |
| <a name="output_public_ip"></a> [public_ip](#output_public_ip)                         | The public IP address of the NAT Gateway.                               |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
