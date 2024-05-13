# pillama
Ansible playbook and Docker compose file for running Ollama on a Raspberry Pi with Multicast
---
To setup, you will need a Raspberry Pi (ideally 4 or higher) running a Debian-based OS (recommended Raspberry Pi OS Lite 64-bit). Optionally, a PC with Ansible installed.

Install the OS and set the hostname to "pillama." This will make the multicast address "pillama.local." Also either set the username to "pi" or change the ansible_user value in inventory.yaml.

Clone this repo and run the playbook:
```
ansible-playbook -i inventory.yaml setup.yaml
```

After it's finished, login to the pi and start the docker images:
```
sudo docker-compose up -d
```
---
If all goes well, in a few minutes you should have a Wifi Network come up called "Pillama-Wifi" with password "pillamawifi". Accessing this Wifi and visiting http://pillama.local should let you login to the WebUI for the Pillama. Download a model and start using your new AI. http://pillama.local should also be reachable from any LAN the pi is connected to a la multicast.

---
---

## Not using a Raspberry Pi, just want an easy way to get Ollama with Open-WebUI up in docker?

Clone this repo and run docker-compose:
```
sudo docker-compose up -d
```
Then access it on the same machine it's installed on at http://localhost or http://127.0.0.1
