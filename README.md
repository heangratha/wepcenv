# wepcenv

# Requirement

	- git
	- ansible v2.x

# Install git

	sudo apt-get install git ansible

# Install ansible

	git clone https://github.com/ansible/ansible.git /var/tmp/ansible
	cd /var/tmp/ansible
	git fetch --all --quiet
	git checkout --quiet stable-2.3
	git submodule update --init --recursive
	make
	sudo make install

# Run ansible playbook to intall common packages require by Web Essentials

	ansible-playbook -i "localhost," -c local playbook.yml --ask-become-pass


