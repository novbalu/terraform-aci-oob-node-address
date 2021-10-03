<!-- BEGIN_TF_DOCS -->
[![Tests](https://github.com/netascode/terraform-aci-oob-node-address/actions/workflows/test.yml/badge.svg)](https://github.com/netascode/terraform-aci-oob-node-address/actions/workflows/test.yml)

# Terraform ACI OOB Node Address Module

Manages ACI OOB Node Address

Location in GUI:
`Tenants` » `mgmt` » `Node Management Addresses` » `Static Node Management Addresses`

## Examples

```hcl
module "aci_oob_node_address" {
  source  = "netascode/oob-node-address/aci"
  version = ">= 0.0.2"

  node_id        = 111
  pod_id         = 2
  ip             = "100.1.1.111/24"
  gateway        = "100.1.1.254"
  endpoint_group = "OOB1"
}

```

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0.0 |
| <a name="requirement_aci"></a> [aci](#requirement\_aci) | >= 0.2.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aci"></a> [aci](#provider\_aci) | >= 0.2.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_node_id"></a> [node\_id](#input\_node\_id) | Node ID. | `number` | n/a | yes |
| <a name="input_pod_id"></a> [pod\_id](#input\_pod\_id) | Pod ID. | `number` | `1` | no |
| <a name="input_ip"></a> [ip](#input\_ip) | OOB IP address. | `string` | n/a | yes |
| <a name="input_gateway"></a> [gateway](#input\_gateway) | OOB gateway IP. | `string` | n/a | yes |
| <a name="input_endpoint_group"></a> [endpoint\_group](#input\_endpoint\_group) | OOB management endpoint group name. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_dn"></a> [dn](#output\_dn) | Distinguished name of `mgmtRsOoBStNode` object. |

## Resources

| Name | Type |
|------|------|
| [aci_rest.mgmtOoB](https://registry.terraform.io/providers/netascode/aci/latest/docs/resources/rest) | resource |
| [aci_rest.mgmtRsOoBStNode](https://registry.terraform.io/providers/netascode/aci/latest/docs/resources/rest) | resource |
<!-- END_TF_DOCS -->