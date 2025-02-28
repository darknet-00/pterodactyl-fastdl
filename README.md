﻿# pterodactyl-fastdl
## Requirements
- Pterodactyl Wings 1.X.X
- Web server like nginx/apache
## Installation
1. Run the command below to assign user www-data to group pterodactyl
    - gpasswd -a www-data pterodactyl

2. Run the commands below to set group permissions for read and exec
    - chmod 755 /var/lib/pterodactyl/
    - chmod 755 /var/lib/pterodactyl/volumes/

3. Add the command below in the last line of Eggs "Install script"
    - chmod 750 /mnt/server/

4. If you currently have servers installed, you can reinstall to set the new permissions or set manually running the command below (change UUID for your game server UUID):
    - chmod 750 /var/lib/pterodactyl/volumes/UUID/

5. Start/Restart new servers to set owner and group of pterodactyl, without this fastdl dont will work on game server.

## nginx
1. See nginx.txt, choose one of the 3 options and replace `<domain>` with a domain name of your fastdl
    - If you chose to use a current nginx config don´t follow the next steps of nginx and only do the step 4 and 5.
2. Save with the name fastdl.conf in the directory /etc/nginx/sites-available/
3. Run the comand below to enable
    - ln -s /etc/nginx/sites-available/fastdl.conf /etc/nginx/sites-enabled/fastdl.conf
4. Reload nginx
    - systemctl reload nginx
5. Visit website of your domain and you should see folders with the name of your game servers UUID, if you have been added index.html, you should only see text:
    - "FastDownload"
## FastDl URL
For example in Counter-Strike is:
 - <span>http://domainORip/UUID/cstrike/</span>
 - To know UUID of a server visit admin panel in servers section
