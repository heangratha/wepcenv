# wepcenv

# Requirement

	- git
	- ansible v2.3

# Add require repository

	sudo apt-get install software-properties-common
	sudo add-apt-repository ppa:ondrej/php
	sudo apt-add-repository ppa:ansible/ansible
	sudo apt-get update

# Install git ansible

	sudo apt-get install git ansible

# Clone repository

  ssh: git clone git@github.com:heangratha/wepcenv.git

  https: git clone https://github.com/heangratha/wepcenv.git

# Run ansible playbook to intall common packages require by Web Essentials

	ansible-playbook -i "localhost," -c local playbook.yml --ask-become-pass

# Add User to Docker group

	sudo usermod -aG docker {USER
