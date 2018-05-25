---
layout: "huaweicloud"
page_title: "Huaweicloud: huaweicloud_cce_nodes_v3"
sidebar_current: "docs-huaweicloud-datasource-cce_nodes-v3"
description: |-
  To get the specified node in a cluster.
---


# huaweicloud_cce_nodes_v3_

To get the specified node in a cluster.

## Example Usage

 ```

    data "huaweicloud_cce_nodes_v3" "node1" 
        {
            cluster_id = "Enter cluster id." 
            node_id = "Enter node id"
        }

    output "resource_data" 
        {
            value = "${data.huaweicloud_cce_nodes_v3.node1.name}"
        }

    output "resource_data1" 
        {
            value = "${data.huaweicloud_cce_nodes_v3.node1.data_volumes}"
        }
		
    output "resource_data2" 
        {
            value = "${data.huaweicloud_cce_nodes_v3.node1.public_ip_ids}"
        }

    output "resource_data3" 
        {
            value = "${data.huaweicloud_cce_nodes_v3.node1.node_id}"
        }

 ```
## Argument Reference

The following arguments are supported:

* `Project_id` -  (Mandatory) The ID of Project.
 
* `Cluster_id` - (Mandatory) The ID of container cluster.

## Attributes Reference

* `kind` - (Required) Kind is a string value representing the REST resource this object represents. 

* `apiVersion` - (Required) APIVersion defines the versioned schema of this representation of an object.

* `node_id` - (Required) 	Node id.

**metadata - (Required)** 

* `name` - (Required) 	Node Name.

**annotations - (Required)** 

* `jobid` - The ID of the Job that is operating asynchronously in the node.
    
**spec - (Required)** 

* `flavor` - For specifications of the node , see Help Center> Elastic Cloud Server >API Reference >Life Cycle Management >Create a description of the "flavorRef " parameter in Cloud Server.

* `az` - Available partitions where the node is located. For details, see Help Center> Elastic Cloud Servers >API Reference >Life Cycle Management >Create a description of the "availability_zone " parameter in the cloud server.

* `sshkey` - Key pair name when logging in to select the key pair mode.

* `billing_mode` - Node's billing mode: The value is 0 (on demand).
    
**rootVolume - (Required)** 

* `size` - Disk size in GB.

**dataVolumes - (Required)** 

* `size` - Disk size in GB.

* `volumetype` - Disk type.

* `extendparam` - Extended parameters.

* `chargemode` - Bandwidth billing type.
 
**status**

* `phase` - The state of the node, the value is Build, Active, Abnormal, Deleting, Installing or Upgrading.

* `server_id` - The node's virtual machine ID in ECS.

* `public_ip` - Elastic IP parameters of the node.

* `private_ip` - Private IP of the node

* `creationtimestamp` - 	node creation timestamp.

* `updatetimestamp` - node update timestamp.

* `reason` - The reason why a node changes to its current state.

* `message` - 	Details of node transition to current state.


