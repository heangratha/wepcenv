# wepcenv

# Requirement

	- git
	- ansible v2.3

# Add require repository

	sudo apt-get install software-properties-common
	sudo add-apt-repository ppa:ondrej/php
	sudo apt-add-repository ppa:ansible/ansible
	sudo apt-ge update

# Install git ansible

	sudo apt-get install git ansible

# Run ansible playbook to intall common packages require by Web Essentials

	ansible-playbook -i "localhost," -c local playbook.yml --ask-become-pass


