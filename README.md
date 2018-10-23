remove_digitalocean_dns_entries
=========

A role to delete DNS entries (A name records) that are listed in your DigitalOcean's DNS/Networking listings.

Requirements
------------

You must use DigitalOcean, have a DO API key setup and have A Name records listed in DigitalOcean's DNS servers that you would like to delete.

Role Variables
--------------

The Fully Qualified Domain Name that you would like to remove from the DigitalOcean DNS  system. This role will also check to see if there is an entry for this same FQDN, but that is pre-pended by a "www" subdomain and will attempt to delete that entry as well.
```
	remove_digitalocean_dns_entries_server_fqdn: "yourdomainhere.com"
```

You must have your DigitalOcean API token saved into this environment variable
```
	remove_digitalocean_dns_entries_do_token: "{{ lookup('env', 'DO_API_TOKEN') }}"
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


	- hosts: localhost ansible_connection=local ansible_python_interpreter=python
	  vars_files:
	    - vars/main.yml
	  roles:
	    - stancel.remove_digitalocean_dns_entries


or 


	- hosts: localhost ansible_connection=local ansible_python_interpreter=python 
	  vars:
		remove_digitalocean_dns_entries_server_fqdn: "mysubdomain.mydomain.com"
		remove_digitalocean_dns_entries_do_token: "{{ lookup('env', 'DO_API_TOKEN') }}"
	  roles:
	    - stancel.remove_digitalocean_dns_entries


License
-------

BSD

Author Information
------------------

[Brad Stancel](https://github.com/stancel)

