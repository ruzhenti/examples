ubu8@ubu8Virt:~$ sudo wget https://download.docker.com/linux/ubuntu/dists/jammy/pool/stable/amd64/docker-ce-cli_20.10.13~3-0~ubuntu-jammy_amd64.deb
[sudo] password for ubu8:
--2023-06-06 22:35:15--  https://download.docker.com/linux/ubuntu/dists/jammy/pool/stable/amd64/docker-ce-cli_20.10.13~3-0~ubuntu-jammy_amd64.deb
Resolving download.docker.com (download.docker.com)... 108.156.22.127, 108.156.22.86, 108.156.22.116, ...
Connecting to download.docker.com (download.docker.com)|108.156.22.127|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 40955778 (39M) [binary/octet-stream]
Saving to: ‘docker-ce-cli_20.10.13~3-0~ubuntu-jammy_amd64.deb’

docker-ce-cli_20.10.13~3- 100%[=====================================>]  39,06M  5,79MB/s    in 6,9s

2023-06-06 22:35:22 (5,65 MB/s) - ‘docker-ce-cli_20.10.13~3-0~ubuntu-jammy_amd64.deb’ saved [40955778/40955778]

ubu8@ubu8Virt:~$ sudo dpkg -i docker-ce-cli_20.10.133-0ubuntu-jammy_amd64.deb
dpkg: error: dpkg frontend lock was locked by another process with pid 4315
Note: removing the lock file is always wrong, and can end up damaging the
locked area and the entire system. See <https://wiki.debian.org/Teams/Dpkg/FAQ>.
ubu8@ubu8Virt:~$
