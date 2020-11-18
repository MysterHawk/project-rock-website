+++
title = "Void linux cheatsheet"
date = 2020-11-18

[taxonomies]
tags = ["voidlinux", "wiki", "cheatsheet"]
+++

This page is dedicated to the most useful commands-line code that I use frequently


### To search a package:
`xbps-query -Rs package_name`

### To update the system:
`sudo xbps-install -Su`
### To add all the most common useful repositories:
```
sudo xbps-install -S void-repo-multilib
sudo xbps-install -S void-repo-nonfree
sudo xbps-install -S void-repo-multilib-nonfree
sudo xbps-install -Su
```
### To install Nvidia drivers:
```
sudo xbps-install nvidia
sudo echo "blacklist nouveau" >> /etc/modprobe.d/blacklist.conf
sudo xbps-reconfigure -f linux[insert version here]

# Now you have 2 choices, you can do it the safe way or alternatively the Russian roulotte way

# Safe way
sudo rm /var/service/[insert login manager here (like lightdm)]
sudo reboot
# Now you don't have a gui but don't worry, try to do:
sudo modprobe nvidia
# if that worked then redo the link of the login manager
ln -s /etc/sv/[insert login manager here (like lightdm)] /var/service/
# then reboot
DONE


# Russian way
sudo reboot
# and pray for the best :^
DONE
```
 
