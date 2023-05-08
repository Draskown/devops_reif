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
- Change `./ansible/site.yml` file to handle custom group (if they were created) and remove `connection: local` line

## Docker
Runs a python script with a flask web-page that sends data from files `mail.txt` and `name.txt` located in `container-data` to the Redis database. The script and the database are both run on separate containers: `python-app` and `redis` respectively.

The web-page is accessible from the `localhost` on port `5000` and can be accessible from any ip. To change the port you'd need to modify the `app.py` file directly and then adjust `docker-compose.yml` to satisfy the preferred port.
Same can be said for the files that are passed to the `python-app` container. Change either the text inside or files themselves and then duplicate the changes inside `docker-compose.yml`

If you want a different index.html - just overwrite the one in the `template` folder. The composing file sends the folder of templates to the container thus its adjusting in this case is unnecessary.
