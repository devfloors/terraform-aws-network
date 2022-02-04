# subnet-group

This module creates following resources.

-   `aws_subnet`
-   `aws_db_subnet_group` (optional)
-   `aws_elasticache_subnet_group` (optional)
-   `aws_redshift_subnet_group` (optional)
-   `aws_neptune_subnet_group` (optional)
-   `aws_docdb_subnet_group` (optional)
-   `aws_dax_subnet_group` (optional)
-   `aws_dms_replication_subnet_group` (optional)

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

| Name                                                                                                                                              | Type     |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [aws_dax_subnet_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/dax_subnet_group)                         | resource |
| [aws_db_subnet_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_subnet_group)                           | resource |
| [aws_dms_replication_subnet_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/dms_replication_subnet_group) | resource |
| [aws_docdb_subnet_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/docdb_subnet_group)                     | resource |
| [aws_elasticache_subnet_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_subnet_group)         | resource |
| [aws_neptune_subnet_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/neptune_subnet_group)                 | resource |
| [aws_redshift_subnet_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/redshift_subnet_group)               | resource |
| [aws_resourcegroups_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/resourcegroups_group)                 | resource |
| [aws_subnet.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/subnet)                                             | resource |

## Inputs

| Name                                                                                                                                          | Description                                                                                                                                                                                    | Type            | Default                   | Required |
| --------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------- | ------------------------- | :------: |
| <a name="input_name"></a> [name](#input_name)                                                                                                 | The name of the subnet group.                                                                                                                                                                  | `string`        | n/a                       |   yes    |
| <a name="input_subnets"></a> [subnets](#input_subnets)                                                                                        | A map of subnet parameters to create subnets for the subnet group.                                                                                                                             | `map(map(any))` | n/a                       |   yes    |
| <a name="input_vpc_id"></a> [vpc_id](#input_vpc_id)                                                                                           | The ID of the VPC which the subnet group belongs to.                                                                                                                                           | `string`        | n/a                       |   yes    |
| <a name="input_assign_ipv6_address_on_creation"></a> [assign_ipv6_address_on_creation](#input_assign_ipv6_address_on_creation)                | Assign IPv6 address on subnet, must be disabled to change IPv6 CIDRs. This is the IPv6 equivalent of map_public_ip_on_launch.                                                                  | `bool`          | `false`                   |    no    |
| <a name="input_cache_subnet_group_enabled"></a> [cache_subnet_group_enabled](#input_cache_subnet_group_enabled)                               | Controls if Elasticache Subnet Group should be created.                                                                                                                                        | `bool`          | `false`                   |    no    |
| <a name="input_cache_subnet_group_name"></a> [cache_subnet_group_name](#input_cache_subnet_group_name)                                        | Desired name for the Elasticache Subnet Group.                                                                                                                                                 | `string`        | `""`                      |    no    |
| <a name="input_customer_owned_ipv4_pool"></a> [customer_owned_ipv4_pool](#input_customer_owned_ipv4_pool)                                     | The customer owned IPv4 address pool. `outpost_arn` argument must be specified when configured.                                                                                                | `string`        | `""`                      |    no    |
| <a name="input_dax_subnet_group_enabled"></a> [dax_subnet_group_enabled](#input_dax_subnet_group_enabled)                                     | Controls if DAX Subnet Group should be created.                                                                                                                                                | `bool`          | `false`                   |    no    |
| <a name="input_dax_subnet_group_name"></a> [dax_subnet_group_name](#input_dax_subnet_group_name)                                              | Desired name for the DAX Subnet Group.                                                                                                                                                         | `string`        | `""`                      |    no    |
| <a name="input_db_subnet_group_enabled"></a> [db_subnet_group_enabled](#input_db_subnet_group_enabled)                                        | Controls if RDS Subnet Group should be created.                                                                                                                                                | `bool`          | `false`                   |    no    |
| <a name="input_db_subnet_group_name"></a> [db_subnet_group_name](#input_db_subnet_group_name)                                                 | Desired name for the RDS Subnet Group.                                                                                                                                                         | `string`        | `""`                      |    no    |
| <a name="input_dms_replication_subnet_group_enabled"></a> [dms_replication_subnet_group_enabled](#input_dms_replication_subnet_group_enabled) | Controls if DMS Replication Subnet Group should be created.                                                                                                                                    | `bool`          | `false`                   |    no    |
| <a name="input_dms_replication_subnet_group_name"></a> [dms_replication_subnet_group_name](#input_dms_replication_subnet_group_name)          | Desired name for the DMS Replication Subnet Group.                                                                                                                                             | `string`        | `""`                      |    no    |
| <a name="input_docdb_subnet_group_enabled"></a> [docdb_subnet_group_enabled](#input_docdb_subnet_group_enabled)                               | Controls if DocumentDB Subnet Group should be created.                                                                                                                                         | `bool`          | `false`                   |    no    |
| <a name="input_docdb_subnet_group_name"></a> [docdb_subnet_group_name](#input_docdb_subnet_group_name)                                        | Desired name for the DocumentDB Subnet Group.                                                                                                                                                  | `string`        | `""`                      |    no    |
| <a name="input_map_customer_owned_ip_on_launch"></a> [map_customer_owned_ip_on_launch](#input_map_customer_owned_ip_on_launch)                | Should be true if network interfaces created in the subnet should be assigned a customer owned IP address.                                                                                     | `bool`          | `false`                   |    no    |
| <a name="input_map_public_ip_on_launch"></a> [map_public_ip_on_launch](#input_map_public_ip_on_launch)                                        | Should be false if you do not want to auto-assign public IP on launch.                                                                                                                         | `bool`          | `false`                   |    no    |
| <a name="input_module_tags_enabled"></a> [module_tags_enabled](#input_module_tags_enabled)                                                    | Whether to create AWS Resource Tags for the module informations.                                                                                                                               | `bool`          | `true`                    |    no    |
| <a name="input_neptune_subnet_group_enabled"></a> [neptune_subnet_group_enabled](#input_neptune_subnet_group_enabled)                         | Controls if Neptune Subnet Group should be created.                                                                                                                                            | `bool`          | `false`                   |    no    |
| <a name="input_neptune_subnet_group_name"></a> [neptune_subnet_group_name](#input_neptune_subnet_group_name)                                  | Desired name for the Neptune Subnet Group.                                                                                                                                                     | `string`        | `""`                      |    no    |
| <a name="input_outpost_arn"></a> [outpost_arn](#input_outpost_arn)                                                                            | The ARN of the Outpost.                                                                                                                                                                        | `string`        | `""`                      |    no    |
| <a name="input_redshift_subnet_group_enabled"></a> [redshift_subnet_group_enabled](#input_redshift_subnet_group_enabled)                      | Controls if Redshift Subnet Group should be created.                                                                                                                                           | `bool`          | `false`                   |    no    |
| <a name="input_redshift_subnet_group_name"></a> [redshift_subnet_group_name](#input_redshift_subnet_group_name)                               | Desired name for the Redshift Subnet Group.                                                                                                                                                    | `string`        | `""`                      |    no    |
| <a name="input_resource_group_description"></a> [resource_group_description](#input_resource_group_description)                               | The description of Resource Group.                                                                                                                                                             | `string`        | `"Managed by Terraform."` |    no    |
| <a name="input_resource_group_enabled"></a> [resource_group_enabled](#input_resource_group_enabled)                                           | Whether to create Resource Group to find and group AWS resources which are created by this module.                                                                                             | `bool`          | `true`                    |    no    |
| <a name="input_resource_group_name"></a> [resource_group_name](#input_resource_group_name)                                                    | The name of Resource Group. A Resource Group name can have a maximum of 127 characters, including letters, numbers, hyphens, dots, and underscores. The name cannot start with `AWS` or `aws`. | `string`        | `""`                      |    no    |
| <a name="input_tags"></a> [tags](#input_tags)                                                                                                 | A map of tags to add to all resources.                                                                                                                                                         | `map(string)`   | `{}`                      |    no    |

## Outputs

| Name                                                                                                                             | Description                                                  |
| -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| <a name="output_arns"></a> [arns](#output_arns)                                                                                  | A list of ARNs of subnets                                    |
| <a name="output_availability_zone_ids"></a> [availability_zone_ids](#output_availability_zone_ids)                               | A list of availability zone IDs which the subnet group uses. |
| <a name="output_availability_zones"></a> [availability_zones](#output_availability_zones)                                        | A list of availability zones which the subnet group uses.    |
| <a name="output_cache_subnet_group_id"></a> [cache_subnet_group_id](#output_cache_subnet_group_id)                               | The ID of the Elasticache Subnet Group.                      |
| <a name="output_cidr_blocks"></a> [cidr_blocks](#output_cidr_blocks)                                                             | The CIDR blocks of the subnet group.                         |
| <a name="output_dax_subnet_group_id"></a> [dax_subnet_group_id](#output_dax_subnet_group_id)                                     | The ID of the DAX Subnet Group.                              |
| <a name="output_db_subnet_group_arn"></a> [db_subnet_group_arn](#output_db_subnet_group_arn)                                     | The ARN of the RDS Subnet Group.                             |
| <a name="output_db_subnet_group_id"></a> [db_subnet_group_id](#output_db_subnet_group_id)                                        | The ID of the RDS Subnet Group.                              |
| <a name="output_dms_replication_subnet_group_id"></a> [dms_replication_subnet_group_id](#output_dms_replication_subnet_group_id) | The ID of the DMS Replication Subnet Group.                  |
| <a name="output_docdb_subnet_group_arn"></a> [docdb_subnet_group_arn](#output_docdb_subnet_group_arn)                            | The ARN of the DocumentDB Subnet Group.                      |
| <a name="output_docdb_subnet_group_id"></a> [docdb_subnet_group_id](#output_docdb_subnet_group_id)                               | The ID of the DocumentDB Subnet Group.                       |
| <a name="output_ids"></a> [ids](#output_ids)                                                                                     | A list of IDs of subnets                                     |
| <a name="output_ipv6_cidr_blocks"></a> [ipv6_cidr_blocks](#output_ipv6_cidr_blocks)                                              | The IPv6 CIDR blocks of the subnet group.                    |
| <a name="output_name"></a> [name](#output_name)                                                                                  | The name of the subnet group.                                |
| <a name="output_neptune_subnet_group_arn"></a> [neptune_subnet_group_arn](#output_neptune_subnet_group_arn)                      | The ARN of the Neptune Subnet Group.                         |
| <a name="output_neptune_subnet_group_id"></a> [neptune_subnet_group_id](#output_neptune_subnet_group_id)                         | The ID of the Neptune DB Subnet Group.                       |
| <a name="output_redshift_subnet_group_arn"></a> [redshift_subnet_group_arn](#output_redshift_subnet_group_arn)                   | The ARN of the Redshift Subnet Group.                        |
| <a name="output_redshift_subnet_group_id"></a> [redshift_subnet_group_id](#output_redshift_subnet_group_id)                      | The ID of the Redshift Subnet Group.                         |
| <a name="output_subnets"></a> [subnets](#output_subnets)                                                                         | A list of subnets.                                           |
| <a name="output_vpc_id"></a> [vpc_id](#output_vpc_id)                                                                            | The ID of the VPC which the subnet group belongs to.         |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
