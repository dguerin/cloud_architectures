# cloud_architectures
A repository of cloud architectures for education and illistration purposes. Most of the examples will be based on Azure technoloties. This will continue to grow over time so keep an eye on this space for more.

---

1. [Basic IaaS Architecture](basic-iaas-architecture)
2. [HA IaaS Architecture](ha-iaas-architecture)

---

## 1. [Basic IaaS Architecture](basic-iaas-architecture)
![Basic IaaS Setup](./designs/1.0_basic_iaas_example.svg)
This is an example architecture for the most basic Infrastructre as a service offerning in Azure. It's really here for illistration pupropses and I would really really not recommend this setup for a production system.


Pros
* Very simple setup
* Cheap option relative to other Paas Offering.

Cons
* Lots to manage yourself - ie updates of the vm and db
* No high avability - in the case of failure of the db or the vm there is no other hot system to take over the workload, thus your system is not available to your users.
* Azure will force at times updates of the VM - your site will be down.
* Does not scale - when you get more traffic than you can handle in the db or vm your appliation will fail.

## 2. [HA IaaS Architecture](ha-iaas-architecture)
![HA IaaS Architecture](./designs/2.0_ha_iaas_example.svg)

Pros
* HA with some redundency - keeps our web service running when a VMS is not available
* Load Balancer failure detection - if a VM or app fails, then the load balancer will remove it from rotation of accepting requests. This our users should experience little to no down time.

Cons
* More complex to manage
* Failure domain is just two VMs - which means if one of vms is gone, that is 50% of our capacity. We are left with just a single VM in the face of any additional failures.
* Limited scalability - we only can scale our workload to the capacity of the VMs. We have options to scale up in size at this point but it's manual.
* Database is still a problem and will be a bottleneck for scaling.