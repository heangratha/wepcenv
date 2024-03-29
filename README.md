# wepcenv for Ubuntu 20.04

## Requirement

    - git
    - ansible v2.8

# Add repository for bionic ubuntu 18.04 for install ansible 2.8

    sudo vi /etc/apt/sources.list
    deb http://security.ubuntu.com/ubuntu bionic-security main

# Add require repository

    sudo apt-get install software-properties-common
    sudo add-apt-repository ppa:ondrej/php
    curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
    sudo apt-add-repository ppa:ansible/ansible-2.8
    sudo apt-get update

# Install git ansible

    sudo apt-get install git ansible=2.8.20-1ppa~focal

# Clone repository

    git clone https://github.com/heangratha/wepcenv.git

# Run ansible playbook to intall common packages require by Web Essentials

    ansible-playbook -i "localhost," -c local playbook.yml --ask-become-pass

# Create User with encrypt home

    apt-get install ecryptfs-utils
    sudo adduser --encrypt-home <USERNAME>

# Add User to Docker group

    sudo usermod -aG docker ${USER}

# Add to OCS inventory

    curl -sS http://deb.ocsinventory-ng.org/pubkey.gpg | sudo apt-key add -
    echo "deb http://deb.ocsinventory-ng.org/ubuntu/ $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/ocsinventory.list
    sudo apt update

### Add OCS inventory agent config

    sudo mkdir /etc/ocsinventory
    sudo vi /etc/ocsinventory/ocsinventory-agent.cfg


        ssl=0
        server=https://inventory.web-essentials.co/ocsinventory

### Install agent and choose no do not run config

    sudo apt install ocsinventory-agent

### Run ocsagent add to server

    sudo ocsinventory-agent
