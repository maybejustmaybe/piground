Pre-reqs:
1. Install ansible via pip, ... 
<TODO more prereqs>

Set up a headless Raspberry PI:
1. Format SD card to ExFAT (w/ name "boot")
2. Flash SD card w/ Rasbian [2019-09-26-raspbian-buster-lite] (using balenaEtcher on mac)
3. Unplug and plug SD card back in
4. Set up wireless configuration
    - Edit `wpa_supplicant.conf` w/ your network info
    - `cp wpa_supplicant.conf $BOOT_DIR` (`/Volumes/boot` on mac)
    - `touch $BOOT_DIR/ssh`
5. Eject SD card, put it into the PI, and turn it on
6. To verify connection: SSH to the PI w/ `pi@raspberrypi.local`
    - NOTE that the default password is `raspberry`
7. Add your SSH pub key to `.ssh/authorized_keys` on the pi
    - This makes the ansible setup easier, but probably could be worked around

# TODO : add basic tools to raspberry pi: tmux, htop

Install IPFS:
1. git clone https://github.com/maybejustmaybe/ansible-ipfs-cluster
2. ansible-playbook -i inventory.yml ipfs.yml

TODO:
1. Private swarm
2. Create a custom nycmesh user

Default ipfs password: defaultipfspassword

