# linode-ansible

This repository contains an Ansible Playbook for setting up the configuration required to setup and run a Minecraft server on a Linode instance.

You could _probably_ run a Minecraft server on a Nanode but I recommend a 2GB 1CPU Linode at the least.

## Prerequisites

The Playbook is configured to run against Linode instances. It can be easily modified to run against _anything_ (including localhost if you really want), however modifiying the host configuration is outside the scope of this readme.

In order to run this playbook, you'll need to install Ansible. If you are on [Linux](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-the-control-machine), Ansible is most likely available from your software repositories. If not, it's available in Pip. If you are on [Windows](https://docs.ansible.com/ansible/latest/user_guide/windows_faq.html#can-ansible-run-on-windows), use the WSL.

Once Ansible is installed, you'll need to install the Roles used in the Playbook from Ansible Galaxy. Run these commands:

* `ansible-galaxy install geerlingguy.security`
* `ansible-galaxy install geerlingguy.docker`
* `ansible-galaxy install oefenweb.ufw`
* `ansible-galaxy install git+https://github.com/Egeeio/gsc-user.git`

## Running the Playbook

Once you've installed Ansible and the roles from Ansible Galaxy: 

1. Add the path to your public key in the `./vars/demo.yml` file. Keep in mind, you must have loaded the same public key onto your Linode instance when you created it.
2. Add the ip address to your Linode instance to the `./inventory` file
3. Run `ansible-playbook demo.yml` from this repo's directory

If you get stuck, watch the video I made here 👉 https://youtu.be/mcP_oxZTW9A
