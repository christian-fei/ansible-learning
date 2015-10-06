when doing rolling deployments (without downtime for the users)
we need some kind of pre and post tasks, instead of just updating the configuration, restarting the service (having little downtime)

we can use ansible to tell the loadbalancer to disable web traffic to a specific node (one at a time), that is being updated.

Ansible [delegation, rolling updates](http://docs.ansible.com/ansible/playbooks_delegation.html)

Ansible [rolling upgrades](http://docs.ansible.com/ansible/guide_rolling_upgrade.html)

ansible has a `pre_tasks` and `post_tasks` attribute as part of a playbook. Perfect for disabling and enabling nodes in a load balancer.

`delegate_to` can be used to run a command of an upgrade on a web node to the load balancer.


