# cloud_architectures
A repo of example cloud architecture designs

1. Basic IaaS Architecture


## 1. Basic IaaS Architecture
![Basic IaaS Setup](./designs/1.0_basic_iaas_example.png)
Pros
* Very simple setup
* Cheap option relative to other Paas Offering.

Cons
* Lost to manage yourself - ie updates
* No high avability - in the case of failure of the db or the vm.
* Azure will force at times updates of the VM - your site will be down.
* Does not scale - when you get more traffic than you can handle in the db or vm your appliation will fail.