---
layout: "huaweicloud"
page_title: "HuaweiCloud: huaweicloud_cce_cluster_v3  "
sidebar_current: "docs-huaweicloud-datasource-cce-cluster-v3"
description: |-
  Get information on Cloud Container Engine(CCE).
---

# huaweicloud_cce_cluster_v3

`huaweicloud_cce_cluster_v3` provides details about all clusters and obtains certificate for accessing cluster information.

## Example Usage

 ```hcl
  data "huaweicloud_cce_cluster_v3" "cluster" 

    {
        name = "${huaweicloud_cce_cluster_v3.cluster_1.name}"

        id= "${huaweicloud_cce_cluster_v3.cluster_1.id}"

        vpc_id = "Enter vpc id"

        vpc_name = "Enter vpc name"

        az = "Enter available zone"

        cluster_type = "VirtualMachine"

        status= "Available"
    }

    output "status" 
    {
        value = "${data.huaweicloud_cce_cluster_v3.cluster.status}"
    }

```

## Argument Reference

The following arguments are supported:

* `Project_id` -  (Mandatory) The ID of Project.
 
* `Cluster_id` - (Mandatory) The ID of container cluster.

* `region` - (Optional) The AZ where the cluster resides.

## Attributes Reference

* `billingMode` - Charging mode of the cluster.

**metadata**

* `name` - Specifies name of the cluster in string format.

* `id` - Specifies ID of the cluster.

**spec**
  
* `flavor` - Specifies cluster specification in string format.

* `version` - The version of cluster in string format.

* `cluster_type` - Specifies cluster type whether it is VirtualMachine, BareMetal, or Windows in string format.

**containerNetwork**

* `container_network_cidr` - Specifies container network segment: 172.16.0.0/16 ~ 172.31.0.0/16. If there is a network segment conflict, it will be automatically reselected.

* `container_network_type` - Specifies container network type: overlay_l2 , underlay_ipvlan or vpc-router.

**hostNetwork**

* `vpc_id` - Specifies ID of the VPC used to create the node.
  
* `subnet_id` - Specifies ID of the subnet used to create the node.

* `highway_subnet_id` - Specifies ID of the high speed network used to create bare metal nodes.

**conditions**

* `status` - Specifies cluster status information.

**endpoints**

* `internal` - The address accessed within the user's subnet.

* `external` - Public network access address.






 


