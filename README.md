arch-bootstrap
==============

Bootstrap a base Arch Linux system from any GNU distro.

Install
=======

    $ wget https://raw.githubusercontent.com/KatsutoshiOtogawa/manjaro-bootstrap/main/manjaro-bootstrap.sh
    # install -m 755 manjaro-bootstrap.sh /usr/local/bin/manjaro-bootstrap

Examples
=========

Create a base arch distribution in directory 'myarch' (currently running arch by default.):

    # manjaro-bootstrap myarch
   
The same but use arch x86_64 and a given repository source:

    # manjaro-bootstrap -a x86_64 -r "https://mirror.kku.ac.th/manjaro/" myarch 

Usage
=====

Once the process has finished, chroot to the destination directory (default user: root/root):

    # chroot destination

Note that some packages require some system directories to be mounted. Some of the commands you can try:

    # mount --types proc /proc myarch/proc
    # mount --rbind       /sys myarch/sys
    # mount --make-rslave      myarch/sys
    # mount --rbind       /dev myarch/dev
    # mount --make-rslave      myarch/dev
    # mount --bind        /run myarch/run
    # mount --make-slave       myarch/run
    
License
=======

This project is licensed under the terms of the MIT license
