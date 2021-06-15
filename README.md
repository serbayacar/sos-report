Role Name
=========

Get your system reports using the `sosreport` for the latest released Linux distros.

Requirements
------------
Before playing this role, the current Ansible 2.9+ software must be installed on your system.  

For Ubuntu/Debian,
```
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

For RedHat/CentOS,
```
sudo yum update
sudo yum install epel-release
sudo yum install
```

If you need a more comprehensive explanation for the installation or if you are using an operating system other than the operating systems listed above, please review [official documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).  

\* There are no extra requirements other than the Ansible. 

Role Variables
--------------
Available variables are listed below, along with default values (see `defaults/main.yml`):

Generic view,

    # sosreport output to?
    tmp_dir: /tmp/
    fetch_to: /tmp/

    # sosreport command variables
    ticket_number: 1001
    costumer: 'test'

    # Specify modules which are used while reporting (comma seperated)
    sos_modules: module1,module2
  

1# Sosreport command to which directory you want to output your system reports on the remote computer (default `/tmp/`). 

    tmp_dir: /tmp/

2# After the reporting process is finished, in which directory you want to save the reports on your local computer ( default `/tmp/`)

    fetch_to: /tmp/

3# Sosreport uses customer or customizable report number features while generating reports.  

    ticket_number: 1001
    costumer: 'test'

4# Which modules do you want sos-report to use while reporting? (comma separated) 

    sos_modules: module1,module2 

Example Playbook
----------------

An existing test role listed below. You can find in `tests/tests.yml`

    - hosts: servers
      become:yes
      gather_facts: yes
      roles:
         - sos-report

License
-------

MIT
