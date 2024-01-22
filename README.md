# Ansible Server Configuration Playbook

## Overview

This Ansible playbook is designed to configure servers based on their roles - web server, database server, and file server. The playbook utilizes Ansible roles to organize and apply server configurations efficiently.

## Project Structure

- **inventory.ini**: Inventory file containing details of target servers and their roles.
- **playbook.yml**: Main Ansible playbook that includes roles based on server roles.
- **roles/**
  - **base/tasks/main.yml**: Base role for sudo user.
  - **web_server/tasks/main.yml**: Role for configuring web servers.
  - **db_server/tasks/main.yml**: Role for configuring database servers.
  - **file_server/tasks/main.yml**: Role for configuring file servers.

## Usage

### 1. Prerequisites

Ensure that Ansible is installed on the machine from which you plan to run the playbook.

```bash
# Install Ansible
sudo apt-get update
sudo apt-get install ansible
```

### 2. Inventory Configuration

Edit the `inventory` file to include the details of your target servers and their roles.

```
[web_servers]
web_server1 ansible_host=web_server1_ip

[db_servers]
db_server1 ansible_host=db_server1_ip

[file_servers]
file_server1 ansible_host=file_server1_ip
```

### 3. Run the Playbook

Execute the playbook by running the following command:

```bash
ansible-playbook bootstrap.yml --ask-become-pass
ansible-playbook sys_config.yml
```

### 4. Verify Configurations

Verify that the configurations were successfully applied on the respective servers.

## Customization

Feel free to customize the roles in the `roles/` directory to match your specific server configurations. Each role may have its own set of variables, tasks, and templates.

## Contributing

If you find any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
