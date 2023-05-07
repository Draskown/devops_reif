# Introduction to DevOps

Ansible and Docker tasks from the Raiffeisenbank course

## Ansible
Updates the localhost, removes the oldest kernel versions except two latest, reboots the hosts. Although the reboot task does not work for the localhost due to the closure of the operating node.
Handles three package managers:

- Pacman

Does not include removing the old kernel versions, because arch-based OS keep only the latest one.

- Apt & Yum

Everything included for the Debian-based systems, althoug could not be tested due to having only Arch-based system available.

To work with your own severs, you should:

- Specify the adresses to the `./ansible/inventories/hosts` file
- Establish the ssh keying by adding them directly to the host declaration or by changing the `./ansible/inventories/hosts/group_vars/servers` file for the servers group. Yet, no one stops you from creating another group(s) and specifying the ssh key for them.
- Change ./ansible/site.yml file to handle custom group (if they were created) and remove `connection: local` line