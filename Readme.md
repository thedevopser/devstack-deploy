# Ansible Playbook for Initial Server Setup

This Ansible playbook is designed to automate the initial setup of an Ubuntu web server. It performs the following tasks:

1. Update the system
2. Install and configure Apache
3. Install PHP and most commonly used modules for databases
4. Install Composer, the dependency manager for PHP
5. Install Node.js
6. Install Docker Community Edition (CE)
7. Install Symfony CLI

## Prerequisites

1. Ansible installed on your local machine or a control server.
2. One or more remote Ubuntu servers where you have SSH access with sudo privileges. The IP addresses of these servers should be included in your Ansible inventory file.

## Usage

1. Clone this repository and navigate into its directory:

```bash
git clone https://github.com/thedevopser/devstack-deploy.git
cd ansible-playbook
```

2. Update the hosts file with the IP address of your remote servers. You can also define server groups if needed.

3. Configuration with vars.yml

The `variables/vars.yml` file is a place where you can define variables that will be used in the playbook. This provides an easy way to customize the playbook to suit your needs without having to modify the playbook itself.

Here is a brief explanation of the variables used in this playbook:

- `php_version`: The specific version of PHP to be installed. For example, `7.4` or `8.0`.

- `nodejs_version`: The specific version of Node.js to be installed. If set to `18.x`, the latest LTS version will be installed.

- `webserver`: The webserver you will install : apache2 or nginx.

- `git_user`: The username that will be set globally for git operations on the webserver.

- `git_email`: The email that will be set globally for git operations on the webserver.

- `ubuntu_user`: The Ubuntu user account that will be used to execute commands on the webserver.

You can modify the values of these variables as needed. For example, to install PHP 7.4 instead of 8.0, you would change the `php_version` variable in `vars.yml` to `7.4`.

Note that changing these variables can affect the behavior of the playbook, so be sure you understand the purpose of a variable before changing its value.

4. Run the Ansible playbook:

```bash
ansible-playbook -i hosts/hosts.yml playbook/deploy.yml
```

This playbook may take some time to run, depending on the speed of your internet connection and that of your remote servers.

Notes
---

This playbook has been tested with Ansible 2.10.8 and Ubuntu 22.04. It may not work with other versions of Ansible or Ubuntu.

Furthermore, please note that the shell commands are written for a Unix-based shell like bash, zsh, or sh. If you're using another type of shell (for example, the Windows command shell), you might need to adjust the commands accordingly.

## Reporting Issues and Requesting Features

If you encounter any issues while using this playbook, or if you have a feature request, please open a ticket on the project's GitHub issue tracker. Make sure to describe the issue or request in detail so that it can be addressed appropriately.

To open a ticket, follow these steps:

1. Go to the project's GitHub page (https://github.com/thedevopser/devstack-deploy).
2. Click on the `Issues` tab.
3. Click on the `New issue` button.
4. Choose either `Bug report` or `Feature request`.
5. Fill in the template with as much detail as possible.
6. Click `Submit new issue`.

Your feedback is greatly appreciated and will help improve the playbook.
