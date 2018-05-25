---
layout: "huaweicloud"
page_title: "huaweicloud: huaweicloud_cce_nodes_v3"
sidebar_current: "docs-huaweicloud-resource-cce_nodes-v3"
description: |-
  Add a node to a container cluster. 
---


# huaweicloud_cce_nodes_v1_
Add a node to a container cluster. 

## Example Usage

 ```
		resource "huaweicloud_cce_node_v3" "node_1" 
			{
  					kind="Node"
  					api_version="v3"
  					name = "test-c2d"
  					flavor="s1.medium"
 					az = "cn-east-2a"
  					sshKey="c2c-keypair"
 			 root_volume 
			 	{
    						size = 40
    						volumetype = "SATA"
  				}
 			 data_volumes = [
			   {	
   						 size = 100
   						 volumetype = "SATA"
			   }
										]
  			node_count = 1
			}

 ```    


## Argument Reference
The following arguments are supported:

* `cluster_id` - (Required) Project ID.

* `kind` - (Required) API type, fixed value Node.

* `api_version` - (Required) API version, fixed value v3.

* `billing_mode` - (Optional) Node's billing mode: The value is 0 (on demand).

* `node_count` - (Required) The number of nodes in batch creation.

**metadata (Required)**

* `name` - (Optional) Node Name.

* `labels` - (Optional) Node tag, key/value pair format.

* `annotations` - (Optional) Node annotation, key/value pair format.

**spec - (Required)** 
    
* `flavor` - (Required) For specifications of the node , see Help Center> Elastic Cloud Server >API Reference >Life Cycle Management >Create a description of the "flavorRef " parameter in Cloud Server.
    
* `az` - (Required) Available partitions where the node is located. For details, see Help Center> Elastic Cloud Servers >API Reference >Life Cycle Management >Create a description of the "availability_zone " parameter in the cloud server.

**Login** **- (Required)**

* `sshkey` - (Required) Key pair name when logging in to select the key pair mode.

**root_volume** **- (Required)** System disk parameters of the node

**data_volumes** **- (Required)** The data disk parameter of the node must currently be a disk
    
* `size` - (Required) Disk size in GB.
    
* `volumetype` - (Required) Disk type.
    
* `extend_param` - (Optional) Disk expansion parameters.

**publicIP - (Optional)** Elastic IP parameters of the node.
    
* `eip_ids` - (Optional) List of existing elastic IP IDs.

* `eip_count` - (Optional) Number of elastic IPs to be dynamically created.

**Eip - (Optional)** Elastic IP parameters

* `iptype` - (Optional) Elastic IP type.

**Bandwidth - (Required)** Elastic IP bandwidth parameters

* `chargemode` - (Optional) Bandwidth billing type.

* `sharetype` - (Optional) Bandwidth sharing type.

* `size` - (Optional) Bandwidth size.


