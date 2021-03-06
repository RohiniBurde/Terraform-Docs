---
layout: "opentelekomcloud"
page_title: "OpenTelekomCloud: opentelekomcloud_cce_nodes_v1"
sidebar_current: "docs-opentelekomcloud-datasource-cce_nodes_v1"
description: |-
  Provides the information about all hosts in a specified cluster.
---

# Data Source: opentelekomcloud_cce_nodes_v1

Provides the information about all hosts in a specified cluster.


## Example Usage

 ```hcl
resource "opentelekomcloud_cce_node_v1" "node_1" {
    "kind": "list",
    "apiVersion": "v1",
    "metadata": {},
    "spec": {
        "hostList": [
            {
                "kind": "host",
                "apiVersion": "v1",
                "metadata": {
                    "name": "Enter the host name",
                    "id": "Enter the uuid",
                    "spaceuuid": "Enter space uuid",
                },
                "spec": {
                    "id": "Enter cluster uuid",
                    "name": "Enter cluster name",
                    "private_ip": "Enter the private ip of the host",
                    "public_ip": "Enter the public ip of the host",
                    "flavor": "Enter the instance type",
                    "cpu": 2,
                    "memory": 4096,
                    "id": "Enter host id",
                    "az": "eu-de-01",
                    "volume": [
                        {
                            "disk_Type": "root",
                            "disk_Size": 40,
                            "volume_Type": "SATA"
                        },
                        {
                            "disk_Type": "data",
                            "disk_Size": 100,
                            "volume_Type": "SATA"
                        }
                    ],
                    "sshkey": "SSHkey-b26e",
                    "replicas": 1,
                    "status": "ACTIVE"
            }
        ]
    }
  }
}

 ```


## Argument Reference

The following arguments are supported:

* `kind` - Kind is a string value representing the REST resource this object represents.

* `apiVersion` - APIVersion defines the versioned schema of this representation of an object.

* `replicas` - Number of host instances.

* `status` - Host status.

 **metadata**  
   
  * `name` - Name must be unique within a namespace. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated.
  
  * `id` - UUID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations. 
 
  * `spaceuuid` - ID of the space where the user resides.

 **spec**
  
 * **hostlist** 
  
   * `id` - Cluster UUID.
  
   * `name` - Cluster name.
  
   * `private_ip` - Private network IP address of the host.
  
   * `public_ip` - Public network IP address of the host.
  
   * `flavor` - Host specifications.
  
   * `cpu` - CPU size measured in cores.
  
   * `memory` - Memory size measured in MB.
  
   * `id` - 	Host UUID.
  
   * `az` - az data center where the host resides.
  
   * `label` - Label attached to the host.
  
   * `sshkey` - 	SSH key used to create the host. 
  
 **volume - Disk information**
  
  * `disk_type` - Disk type, which is used to determine a data disk or a system disk.
  
  * `disk_size` - Disk size.

  * `volume_type` - Disk IO type.








