# gcpnatha
How to set up multiple NAT gateways with Equal Cost Multi-Path (ECMP) routing and autohealing enabled for a more resilient and high-bandwidth deployment using Deployment Manager.

* vpcName: the name for the new custom VPC
* ipRange: the CIDR range for the subnetwork for the new VPC
* region: the desired region where we are going to create our resources
* zone[1–3]: the different zones inside the region to create our high availability solution
* sshAccess: a good practice is to restrict the ssh access to our servers and only open from our facilities (I put 0.0.0.0/0 to avoid to put my ip)
* machineType: select the desired instance type

To launch the deploy:
```
gcloud deployment-manager deployments create test-nat-ha --config nat_ha.yaml
```

To delete all the resources:
```
gcloud deployment-manager deployments delete test-nat-ha
```
