# CachyOS Setup Playbook

A simple Ansible playbook for local CachyOS setup that:

1. Enables CachyOS ZEN v4 repositories
2. Installs packages from a customizable list
3. Configures Brave browser policies

## Usage

Run the full playbook:
```bash
ansible-playbook -K local_setup.yml
```

Run specific parts using tags:
```bash
# Only install packages
ansible-playbook -K local_setup.yml --tags packages

# Only configure Brave policies
ansible-playbook -K local_setup.yml --tags policies
```

## Customization

Modify the `vars/packages.yml` file to add or remove packages to install.

The Brave browser policy file (`files/anti-eich-action.json`) disables Brave Rewards, Wallet, VPN, and other unwanted features while setting Kagi as the default new tab page.

## Structure

- `local_setup.yml` - Main playbook
- `tasks/` - Individual task files
- `vars/packages.yml` - List of packages to install
- `files/anti-eich-action.json` - Brave policy configuration
