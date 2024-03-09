

<p align="center">
  <img src="https://github.com/alvarorichard/EpicShelterX/assets/88117897/ced94af7-e1a3-46a0-bb75-4360c5530937" alt="Imagem logo" />
</p>





## EpicShelterX

This Ansible playbook automates a comprehensive user environment setup on a target Ubuntu machine. It handles system updates, utility package installations, user management, sudo privileges, Zsh shell plugins, and ShadowSocks server configuration.

## Features:

## System Setup

System Setup
* Updates all system packages to their latest versions.

## Package Installation

* Installs predefined utility packages like htop, neofetch, git, zsh, etc.

## User Management

* Creates a new user with a specific username.
* Sets Zsh as the default shell for the new user.

## Sudo Configuration

* Configures sudo to allow the new user to execute any command without requiring a password.

## Shell Customization

* Installs Zsh plugins:

* zsh-syntax-highlighting
* fzf
* zsh-autosuggestions
* k

## ShadowSocks Server Configuration

* Pulls the latest ShadowSocks server image from GitHub Container Registry.
* Configures and runs a ShadowSocks server container using Docker.


## Prerequisites

*  Ansible installed on the control node (the machine running the playbook).
* Target machine running Ubuntu or Debain.
* SSH access to the target machine.

## Variables

Customize the playbook by editing variables in a vars.yml file. For instance:

* username: Username for the new user.
* extra_packages: List of additional utility packages to install.
* shadowsocks_port: Port on which the ShadowSocks server will listen.


## How to Run

```bash
git clone https://github.com/alvarorichard/EpicShelterX.git
cd EpicShelterX
```

* 2. Edit the hosts.ini File


Add your target machine details.

```bash
[target]
target_machine ansible_host=your_ip_here ansible_port=your_port_here ansible_user=your_user_here
```
3. Customize Variables

Open the vars.yml file and edit the variables as needed.

4. Run the Playbook
   
Execute the command:

```bash
ansible-playbook -i hosts.ini main.yml -K
```

The -K flag will prompt you for the sudo password, if necessary.

5. Verify Installation

SSH into the target machine to verify if everything is set up correctly.

```bash
ssh username@target_machine_ip
```

## Support
For issues or queries, please open an issue on GitHub.





