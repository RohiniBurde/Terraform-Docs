---
layout: "huaweicloud"
page_title: "huaweicloud: huaweicloud_cce_cluster_v3 "
sidebar_current: "docs-huaweicloud-resource-cce-cluster-v3"
description: |-
  Provides Cloud Container Engine(CCE) resource.
---

# huaweicloud_resource_huaweicloud_cce_cluster_v3  

Manages a Cloud Contianer Engine(CCE) resource within Huawei cloud.

## Example Usage

 ```hcl
	resource "huaweicloud_cce_cluster_v3" "cluster_1" 
	
	{
 
     kind= "Cluster"
     api_version= "v3"
     name = "Enter cluster name"
     cluster_type= "Enter cluster type"
     flavor= "Enter flavor id"
     cluster_version= "v1.7.3-r10"
     vpc_id= "Enter vpc id"
     subnet_id= "Enter subnet id"
     container_network_type= "Enter container network type"
     description= "Enter description"
	}
```

## Argument Reference

The following arguments are supported:

* `kind` - (Required) API type, fixed value Cluster.

* `apiVersion` - (Required) API version, fixed value v3.

* `name` - (Required) Cluster name.

* `labels` - (Optional) Cluster tag, key/value pair format.

* `annotations` - (Optional) Cluster annotation, key/value pair format.

* `flavor` - (Required) Cluster specifications.

* `cluster_version` - (Optional) For the cluster version, please fill in v1.7.3-r10 or v1.9.2-r1. Currently only Kubernetes 1.7 and 1.9 clusters are supported.

* `cluster_type` - (Required) Cluster Type: VirtualMachine, BareMetal, or Windows.

* `description` - (Optional) Cluster description.

* `billing_mode` - (Optional) Charging mode of the cluster, which is 0 (on demand).

* `extend_param` - (Optional) 

**hostNetwok - (Required)** Node network parameters

  * `vpc_id` - (Required) The ID of the VPC used to create the node.

  * `subnet_id` - (Required) The ID of the subnet used to create the node.

  * `highway_subnet_id` - (Optional) The ID of the high speed network used to create bare metal nodes.

**container_network_type** **- (Required)** Container network parameters.

  * `container_network_cidr` - (Optional) Container network segment: 172.16.0.0/16 ~ 172.31.0.0/16. If there is a network segment conflict, it will be automatically reselected.

## Attributes Reference

The following attributes are exported:

**status - (Required)** Cluster status information.

   * `internal_endpoint` - (Optional) The address accessed within the user's subnet

   * `external_endpoint` - (Optional) Public network access address.
 


