# security-group

This module creates following resources.

-   `aws_security_group`
-   `aws_security_group_rule` (optional)

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

| Name                                                                                                                               | Type     |
| ---------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [aws_resourcegroups_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/resourcegroups_group)  | resource |
| [aws_security_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)              | resource |
| [aws_security_group_rule.egress](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule)  | resource |
| [aws_security_group_rule.ingress](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |

## Inputs

| Name                                                                                                            | Description                                                                                                                                                                                    | Type          | Default                   | Required |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------------------- | :------: |
| <a name="input_vpc_id"></a> [vpc_id](#input_vpc_id)                                                             | The ID of the associated VPC.                                                                                                                                                                  | `string`      | n/a                       |   yes    |
| <a name="input_description"></a> [description](#input_description)                                              | The security group description. This field maps to the AWS `GroupDescription` attribute, for which there is no Update API.                                                                     | `string`      | `"Managed by Terraform."` |    no    |
| <a name="input_egress_rules"></a> [egress_rules](#input_egress_rules)                                           | A list of egress rules in a security group.                                                                                                                                                    | `any`         | `[]`                      |    no    |
| <a name="input_ingress_rules"></a> [ingress_rules](#input_ingress_rules)                                        | A list of ingress rules in a security group.                                                                                                                                                   | `any`         | `[]`                      |    no    |
| <a name="input_module_tags_enabled"></a> [module_tags_enabled](#input_module_tags_enabled)                      | Whether to create AWS Resource Tags for the module informations.                                                                                                                               | `bool`        | `true`                    |    no    |
| <a name="input_name"></a> [name](#input_name)                                                                   | The name of the security group. If omitted, Terraform will assign a random, unique name.                                                                                                       | `string`      | `null`                    |    no    |
| <a name="input_name_prefix"></a> [name_prefix](#input_name_prefix)                                              | Creates a unique name beginning with the specified prefix. Conflicts with `name`.                                                                                                              | `string`      | `null`                    |    no    |
| <a name="input_resource_group_description"></a> [resource_group_description](#input_resource_group_description) | The description of Resource Group.                                                                                                                                                             | `string`      | `"Managed by Terraform."` |    no    |
| <a name="input_resource_group_enabled"></a> [resource_group_enabled](#input_resource_group_enabled)             | Whether to create Resource Group to find and group AWS resources which are created by this module.                                                                                             | `bool`        | `true`                    |    no    |
| <a name="input_resource_group_name"></a> [resource_group_name](#input_resource_group_name)                      | The name of Resource Group. A Resource Group name can have a maximum of 127 characters, including letters, numbers, hyphens, dots, and underscores. The name cannot start with `AWS` or `aws`. | `string`      | `""`                      |    no    |
| <a name="input_revoke_rules_on_delete"></a> [revoke_rules_on_delete](#input_revoke_rules_on_delete)             | Instruct Terraform to revoke all of the Security Groups attached ingress and egress rules before deleting the rule itself. This is normally not needed.                                        | `bool`        | `false`                   |    no    |
| <a name="input_tags"></a> [tags](#input_tags)                                                                   | A map of tags to add to all resources.                                                                                                                                                         | `map(string)` | `{}`                      |    no    |

## Outputs

| Name                                                        | Description                                             |
| ----------------------------------------------------------- | ------------------------------------------------------- |
| <a name="output_arn"></a> [arn](#output_arn)                | The ARN of the security group.                          |
| <a name="output_id"></a> [id](#output_id)                   | The ID of the security group.                           |
| <a name="output_name"></a> [name](#output_name)             | The name of the security group.                         |
| <a name="output_owner_id"></a> [owner_id](#output_owner_id) | The ID of the AWS account that owns the security group. |
| <a name="output_vpc_id"></a> [vpc_id](#output_vpc_id)       | The ID of the associated VPC.                           |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
