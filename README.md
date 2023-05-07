# Introduction to DevOps

Ansible and docker tasks from the Raiffeisenbank course

## Ansible
Updates the localhost, removes the oldest kernel versions except two latest, reboots the hosts. Although the reboot task does not work for the localhost due to the closure of the operating node.
Handles three package managers:

- Pacman

Does not include removing the old kernel versions, because arch-based OS keep only the latest one.

- Apt & Yum

Everything included for the Debian-based systems, althoug could not be tested due to having only Arch-based system available.
