Microsoft Windows [Version 10.0.19044.2965]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\User>ssh ubu8@192.168.0.28
ubu8@192.168.0.28's password:
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.19.0-43-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

336 updates can be applied immediately.
173 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Last login: Mon Jun  5 23:05:10 2023 from 192.168.0.19
ubu8@ubu8Virt:~$ mkdir nursery
ubu8@ubu8Virt:~$ cd nursery
ubu8@ubu8Virt:~/nursery$ cat pet_animals
cat: pet_animals: No such file or directory
ubu8@ubu8Virt:~/nursery$ cat > pet_animals
^C
ubu8@ubu8Virt:~/nursery$ cat pack_animals
cat: pack_animals: No such file or directory
ubu8@ubu8Virt:~/nursery$ cat > pack_animals
^C
ubu8@ubu8Virt:~/nursery$ ls
pack_animals  pet_animals
ubu8@ubu8Virt:~/nursery$ cat pet_animals pack_animals > animals
ubu8@ubu8Virt:~/nursery$ cat animals
ubu8@ubu8Virt:~/nursery$ ls
animals  pack_animals  pet_animals
ubu8@ubu8Virt:~/nursery$ mv animals mans_friends
ubu8@ubu8Virt:~/nursery$ ls
mans_friends  pack_animals  pet_animals
ubu8@ubu8Virt:~/nursery$