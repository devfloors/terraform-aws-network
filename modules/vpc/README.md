# vpc

This module creates following resources.

-   `aws_vpc`
-   `aws_vpc_ipv4_cidr_block_association` (optional)
-   `aws_route53_zone_association` (optional)
-   `aws_vpc_dhcp_options` (optional)
-   `aws_vpc_dhcp_options_association` (optional)
-   `aws_internet_gateway` (optional)
-   `aws_egress_only_internet_gateway` (optional)
-   `aws_vpn_gateway` (optional)

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

| Name                                                                                                                                                    | Type        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| [aws_egress_only_internet_gateway.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/egress_only_internet_gateway)       | resource    |
| [aws_internet_gateway.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/internet_gateway)                               | resource    |
| [aws_resourcegroups_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/resourcegroups_group)                       | resource    |
| [aws_route53_resolver_dnssec_config.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route53_resolver_dnssec_config)   | resource    |
| [aws_route53_zone_association.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route53_zone_association)               | resource    |
| [aws_vpc.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc)                                                         | resource    |
| [aws_vpc_dhcp_options.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_dhcp_options)                               | resource    |
| [aws_vpc_dhcp_options_association.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_dhcp_options_association)       | resource    |
| [aws_vpc_ipv4_cidr_block_association.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_ipv4_cidr_block_association) | resource    |
| [aws_vpn_gateway.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpn_gateway)                                         | resource    |
| [aws_region.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/region)                                             | data source |

## Inputs

| Name                                                                                                                                          | Description                                                                                                                                                                                    | Type           | Default                                   | Required |
| --------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- | ----------------------------------------- | :------: |
| <a name="input_name"></a> [name](#input_name)                                                                                                 | Desired name for the VPC resources.                                                                                                                                                            | `string`       | n/a                                       |   yes    |
| <a name="input_cidr_block"></a> [cidr_block](#input_cidr_block)                                                                               | The CIDR block for the VPC. Default value is a valid CIDR, but not acceptable by AWS and should be overridden.                                                                                 | `string`       | `"0.0.0.0/0"`                             |    no    |
| <a name="input_dhcp_options_domain_name"></a> [dhcp_options_domain_name](#input_dhcp_options_domain_name)                                     | Specifies DNS name for DHCP options set (requires enable_dhcp_options set to true).                                                                                                            | `string`       | `""`                                      |    no    |
| <a name="input_dhcp_options_domain_name_servers"></a> [dhcp_options_domain_name_servers](#input_dhcp_options_domain_name_servers)             | Specify a list of DNS server addresses for DHCP options set, default to AWS provided (requires enable_dhcp_options set to true).                                                               | `list(string)` | <pre>[<br> "AmazonProvidedDNS"<br>]</pre> |    no    |
| <a name="input_dhcp_options_enabled"></a> [dhcp_options_enabled](#input_dhcp_options_enabled)                                                 | Should be true if you want to specify a DHCP options set with a custom domain name, DNS servers, NTP servers, netbios servers, and/or netbios server type.                                     | `bool`         | `false`                                   |    no    |
| <a name="input_dhcp_options_netbios_name_servers"></a> [dhcp_options_netbios_name_servers](#input_dhcp_options_netbios_name_servers)          | Specify a list of netbios servers for DHCP options set (requires enable_dhcp_options set to true).                                                                                             | `list(string)` | `[]`                                      |    no    |
| <a name="input_dhcp_options_netbios_node_type"></a> [dhcp_options_netbios_node_type](#input_dhcp_options_netbios_node_type)                   | Specify netbios node_type for DHCP options set (requires enable_dhcp_options set to true).                                                                                                     | `string`       | `""`                                      |    no    |
| <a name="input_dhcp_options_ntp_servers"></a> [dhcp_options_ntp_servers](#input_dhcp_options_ntp_servers)                                     | Specify a list of NTP servers for DHCP options set (requires enable_dhcp_options set to true).                                                                                                 | `list(string)` | `[]`                                      |    no    |
| <a name="input_dns_dnssec_validation_enabled"></a> [dns_dnssec_validation_enabled](#input_dns_dnssec_validation_enabled)                      | Should be true to enable Route53 DNSSEC validation in the VPC.                                                                                                                                 | `bool`         | `false`                                   |    no    |
| <a name="input_dns_hostnames_enabled"></a> [dns_hostnames_enabled](#input_dns_hostnames_enabled)                                              | Should be true to enable DNS hostnames in the VPC.                                                                                                                                             | `bool`         | `false`                                   |    no    |
| <a name="input_dns_support_enabled"></a> [dns_support_enabled](#input_dns_support_enabled)                                                    | Should be true to enable DNS support in the VPC.                                                                                                                                               | `bool`         | `true`                                    |    no    |
| <a name="input_egress_only_internet_gateway_enabled"></a> [egress_only_internet_gateway_enabled](#input_egress_only_internet_gateway_enabled) | Should be true if you want to create a new Egress Only Internet Gateway resource and attach it to the VPC.                                                                                     | `bool`         | `false`                                   |    no    |
| <a name="input_instance_tenancy"></a> [instance_tenancy](#input_instance_tenancy)                                                             | A tenancy option for instances launched into the VPC. Only support `default` or `dedicated`.                                                                                                   | `string`       | `"default"`                               |    no    |
| <a name="input_internet_gateway_enabled"></a> [internet_gateway_enabled](#input_internet_gateway_enabled)                                     | Should be true if you want to create a new Internet Gateway resource and attach it to the VPC.                                                                                                 | `bool`         | `true`                                    |    no    |
| <a name="input_ipv6_enabled"></a> [ipv6_enabled](#input_ipv6_enabled)                                                                         | Requests an Amazon-provided IPv6 CIDR block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or the size of the CIDR block.                                 | `bool`         | `false`                                   |    no    |
| <a name="input_module_tags_enabled"></a> [module_tags_enabled](#input_module_tags_enabled)                                                    | Whether to create AWS Resource Tags for the module informations.                                                                                                                               | `bool`         | `true`                                    |    no    |
| <a name="input_private_hosted_zones"></a> [private_hosted_zones](#input_private_hosted_zones)                                                 | List of private Hosted Zone IDs to associate.                                                                                                                                                  | `list(string)` | `[]`                                      |    no    |
| <a name="input_resource_group_description"></a> [resource_group_description](#input_resource_group_description)                               | The description of Resource Group.                                                                                                                                                             | `string`       | `"Managed by Terraform."`                 |    no    |
| <a name="input_resource_group_enabled"></a> [resource_group_enabled](#input_resource_group_enabled)                                           | Whether to create Resource Group to find and group AWS resources which are created by this module.                                                                                             | `bool`         | `true`                                    |    no    |
| <a name="input_resource_group_name"></a> [resource_group_name](#input_resource_group_name)                                                    | The name of Resource Group. A Resource Group name can have a maximum of 127 characters, including letters, numbers, hyphens, dots, and underscores. The name cannot start with `AWS` or `aws`. | `string`       | `""`                                      |    no    |
| <a name="input_secondary_cidr_blocks"></a> [secondary_cidr_blocks](#input_secondary_cidr_blocks)                                              | List of secondary CIDR blocks to associate with the VPC to extend the IP Address pool.                                                                                                         | `list(string)` | `[]`                                      |    no    |
| <a name="input_tags"></a> [tags](#input_tags)                                                                                                 | A map of tags to add to all resources.                                                                                                                                                         | `map(string)`  | `{}`                                      |    no    |
| <a name="input_vpn_gateway_asn"></a> [vpn_gateway_asn](#input_vpn_gateway_asn)                                                                | The Autonomous System Number (ASN) for the Amazon side of the gateway. By default the virtual private gateway is created with the current default Amazon ASN.                                  | `string`       | `"64512"`                                 |    no    |
| <a name="input_vpn_gateway_enabled"></a> [vpn_gateway_enabled](#input_vpn_gateway_enabled)                                                    | Should be true if you want to create a new VPN Gateway resource and attach it to the VPC.                                                                                                      | `bool`         | `false`                                   |    no    |

## Outputs

| Name                                                                                                                                            | Description                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <a name="output_arn"></a> [arn](#output_arn)                                                                                                    | The ARN of the VPC.                                                                                                                                           |
| <a name="output_cidr_block"></a> [cidr_block](#output_cidr_block)                                                                               | The CIDR block of the VPC.                                                                                                                                    |
| <a name="output_default_network_acl_id"></a> [default_network_acl_id](#output_default_network_acl_id)                                           | The ID of the default network ACL.                                                                                                                            |
| <a name="output_default_route_table_id"></a> [default_route_table_id](#output_default_route_table_id)                                           | The ID of the default route table.                                                                                                                            |
| <a name="output_default_security_group_id"></a> [default_security_group_id](#output_default_security_group_id)                                  | The ID of the security group created by default on VPC creation.                                                                                              |
| <a name="output_dhcp_options_arn"></a> [dhcp_options_arn](#output_dhcp_options_arn)                                                             | The ARN of the DHCP Options Set.                                                                                                                              |
| <a name="output_dhcp_options_enabled"></a> [dhcp_options_enabled](#output_dhcp_options_enabled)                                                 | Whether DHCP options set is enabled in the VPC.                                                                                                               |
| <a name="output_dhcp_options_id"></a> [dhcp_options_id](#output_dhcp_options_id)                                                                | The ID of the DHCP Options Set.                                                                                                                               |
| <a name="output_dns_dnssec_validation_enabled"></a> [dns_dnssec_validation_enabled](#output_dns_dnssec_validation_enabled)                      | Whether or not the VPC has Route53 DNSSEC validation support.                                                                                                 |
| <a name="output_dns_dnssec_validation_id"></a> [dns_dnssec_validation_id](#output_dns_dnssec_validation_id)                                     | The ID of a configuration for DNSSEC validation.                                                                                                              |
| <a name="output_dns_hostnames_enabled"></a> [dns_hostnames_enabled](#output_dns_hostnames_enabled)                                              | Whether or not the VPC has DNS hostname support.                                                                                                              |
| <a name="output_dns_support_enabled"></a> [dns_support_enabled](#output_dns_support_enabled)                                                    | Whether or not the VPC has DNS support.                                                                                                                       |
| <a name="output_egress_only_internet_gateway_enabled"></a> [egress_only_internet_gateway_enabled](#output_egress_only_internet_gateway_enabled) | Whether Egress Only Internet Gateway is enabled in the VPC.                                                                                                   |
| <a name="output_egress_only_internet_gateway_id"></a> [egress_only_internet_gateway_id](#output_egress_only_internet_gateway_id)                | The ID of the Egress Only Internet Gateway.                                                                                                                   |
| <a name="output_id"></a> [id](#output_id)                                                                                                       | The ID of the VPC.                                                                                                                                            |
| <a name="output_instance_tenancy"></a> [instance_tenancy](#output_instance_tenancy)                                                             | Tenancy of instances spin up within VPC.                                                                                                                      |
| <a name="output_internet_gateway_arn"></a> [internet_gateway_arn](#output_internet_gateway_arn)                                                 | The ARN of the Internet Gateway.                                                                                                                              |
| <a name="output_internet_gateway_enabled"></a> [internet_gateway_enabled](#output_internet_gateway_enabled)                                     | Whether Internet Gateway is enabled in the VPC.                                                                                                               |
| <a name="output_internet_gateway_id"></a> [internet_gateway_id](#output_internet_gateway_id)                                                    | The ID of the Internet Gateway.                                                                                                                               |
| <a name="output_ipv6_association_id"></a> [ipv6_association_id](#output_ipv6_association_id)                                                    | The association ID for the IPv6 CIDR block.                                                                                                                   |
| <a name="output_ipv6_cidr_block"></a> [ipv6_cidr_block](#output_ipv6_cidr_block)                                                                | The IPv6 CIDR block.                                                                                                                                          |
| <a name="output_main_route_table_id"></a> [main_route_table_id](#output_main_route_table_id)                                                    | The ID of the main route table associated with this VPC. Note that you can change a VPC's main route table.                                                   |
| <a name="output_name"></a> [name](#output_name)                                                                                                 | The VPC name.                                                                                                                                                 |
| <a name="output_private_hosted_zones"></a> [private_hosted_zones](#output_private_hosted_zones)                                                 | List of associated private Hosted Zone IDs.                                                                                                                   |
| <a name="output_secondary_cidr_blocks"></a> [secondary_cidr_blocks](#output_secondary_cidr_blocks)                                              | List of secondary CIDR blocks of the VPC.                                                                                                                     |
| <a name="output_vpn_gateway_arn"></a> [vpn_gateway_arn](#output_vpn_gateway_arn)                                                                | The ARN of the Virtual Private Gateway.                                                                                                                       |
| <a name="output_vpn_gateway_asn"></a> [vpn_gateway_asn](#output_vpn_gateway_asn)                                                                | The Autonomous System Number (ASN) for the Amazon side of the gateway. By default the virtual private gateway is created with the current default Amazon ASN. |
| <a name="output_vpn_gateway_enabled"></a> [vpn_gateway_enabled](#output_vpn_gateway_enabled)                                                    | Whether VPN Gateway is enabled in the VPC.                                                                                                                    |
| <a name="output_vpn_gateway_id"></a> [vpn_gateway_id](#output_vpn_gateway_id)                                                                   | The ID of the Virtual Private Gateway.                                                                                                                        |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->