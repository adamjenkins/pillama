# pillama
Ansible playbook and Docker compose file for running Ollama on a Raspberry Pi with Multicast
---
To setup, you will need a Raspberry Pi (ideally 4 or higher) running a Debian-based OS (recommended Raspberry Pi OS Lite 64-bit). Optionally, a PC with Ansible installed.

Install the OS and set the hostname to "pillama." This will make the multicast address "pillama.local." Also either set the username to "pi" or change the ansible_user value in inventory.yaml.

Clone this repo and run the playbook:

ansible-playbook -i inventory.yaml setup.yaml

---
If all goes well, in a few minutes you should have a Wifi Network come up called "Pillama-Wifi" with password "pillama". Accessing this Wifi and visiting http://pillama.local should let you login to the WebUI for the Pillama. Download a model and start using your new AI. http://pillama.local should also be reachable from any LAN the pi is connected to a la multicast.
