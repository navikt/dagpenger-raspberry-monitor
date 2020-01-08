# Team Dagpenger's raspberry pi monitoring (forked from Aura)


## Setting up

```
make
```

## Provisioning SD card
This provisioner will format your SD card with Raspbian, deploy a `wpa_supplicant.conf` file, 
and modify its `/etc/rc.local` so that the script `firstboot.sh` runs (on every boot).

Insert SD card, then:
```
./provision \
    -v \
    -board raspberrypi \
    -wifi-ssid <SSID> \
    -wifi-psk <PSK>
```

## Bootstrap
Make sure `inventory.yaml` is up to date. (To add a new host, boot up the raspberry pi, then add the IP adress
displayed on screen to the `inventory.yaml` file and give it a hostname before continuing.)
```
ansible-playbook playbook.yml -b -i inventory.yaml
```
(Using the password for the pi user on the hosts.)

## Map host to Grafana board
Make sure `screenMap.json` is up to date and pushed to github. This maps which website (grafana board usually) 
each host will display. Each host fetches the screenmap from github, so changes 
must be pushed to github to take effect.

## Get token to access grafana 

TODO! 
