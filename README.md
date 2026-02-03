# speedtest-ansible
Ansible playbook for deploying a speedtest tracker container. Speedtest tracker monitors the performance and uptime of your internet connection.

## Install & setup
To use this repo, a couple of tools are required:

* git (to clone the repo)
* pipx (to install ansible)
* ansible (to configure the system)

1 - Oneliner to install all above:
```bash
sudo apt update && sudo apt install -y git pipx && pipx ensurepath && . ~/.profile && pipx install ansible --include-deps
```

2 - Clone this repository:
```bash
git clone https://github.com/fjfinch/speedtest-ansible.git
```

3 - Pull the required roles:
```bash
ansible-galaxy collection install -r requirements.yml
```

4 - Execute the playbook:
> Note: first create the file `files/env/speedtest_secrets.env` with the variable *APP\_KEY=''* in it. Then generate the key with *echo -n 'base64:'; openssl rand -base64 32;*
```bash
ansible-playbook main.yml -K
```
