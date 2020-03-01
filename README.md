Set up a headless Raspberry PI:
1. Flash SD card w/ Rasbian 
    - RPI version: 2019-09-26-raspbian-buster-lite)
    - Using [balenaEtcher](https://www.balena.io/etcher/)
2. Unplug and plug SD card back in
3. Set up wireless configuration (optional)
    - Edit `./wpa_supplicant.conf` w/ your network info
    - `cp wpa_supplicant.conf $BOOT_DIR` (`/Volumes/boot` on mac)
    - `touch $BOOT_DIR/ssh`
    - NOTE that this process needs to be done everytime the pi is rebooted
4. Eject SD card, put it into the PI, and turn it on
5. To verify connection: SSH to the PI w/ `pi@raspberrypi.local`
    - NOTE that the default password is `raspberry`
6. Add your SSH pub key to `~/.ssh/authorized_keys` on the pi
    - This makes the ansible setup easier, but probably could be worked around

# TODO : add basic tools to raspberry pi: tmux, htop, lsof

Install IPFS:
# TODO : use an isolated environment
1. Install ansible: `pip isntall ansible`
2. Add new host to ansible setup (see `./ansible-pi-setup/host_vars/README.md`)
3. IPFS: `ansible-playbook -i inventory.yml ipfs.yml`
4. and IPFS Cluster: `ansible-playbook -i inventory.yml ipfs-cluster.yml`

# TODO : Create a custom nycmesh user

