# Independent Cloud Rollouts
### v0.1 3/2/21

The two Playbooks *rollout_ec2.yml* and *rollput_gcp.yml* deploy a bunch of VMs, defined in the corresponding Vars files *ec2_vars.yml* or *gcp_vars.yml* to AWS or GCP. Both Playbooks write the outcome of the Cloud rollout to a static inventory file. The format of the inventory is independent of the cloud the VMs have been rolled out. So a follow-up Playbook that installs & Configures an application runs independent of the chosen cloud.

The output format of the inventory:
``` 
[(header of your choosing)]
<public VM IP> vmname=<given vm name> privateip=<cloud internal priivate IP> purpose=<given purpose>
```
Feel free to extend the array in the variable declaration with custom values to be added to the inventory.
