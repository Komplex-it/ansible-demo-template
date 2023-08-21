# Ansible Repository Template

This repository serves as a template for organizing and managing Ansible playbooks, roles, and inventory files. It provides a structure and guidelines to help you maintain a consistent and scalable Ansible project.

## Getting Started

To start using this repository template, follow the steps below:

1. Clone this repository: `git clone https://github.com/your-username/ansible-repository-template.git`
2. Customize the repository as per your requirements.
3. Install Ansible on your local machine or the target server(s) where you plan to run the playbooks. Refer to the [Ansible documentation](https://docs.ansible.com/ansible/latest/installation_guide/index.html) for installation instructions.
4. Update the `inventory/hosts` file with the appropriate host and group information for your environment.
5. Create your Ansible playbooks, roles, and tasks based on your requirements. You can use the `playbooks/` and `roles/` directories as a starting point and modify them accordingly.
6. Execute the playbooks using the `ansible-playbook` command. For example:


## Repository Structure

The repository follows a standard structure to organize Ansible assets. Here is an overview of the main directories:

- `playbooks/`: Holds the Ansible playbooks.
- `roles/`: Includes reusable roles that can be included in multiple playbooks.
- `templates/`: Contains template files that can be used with the `template` module.
- `files/`: Holds files that can be transferred to remote hosts using the `copy` or `fetch` modules.
- `library/`: Directory to store custom Ansible modules.
- `filter_plugins/`: Contains custom filter plugins.

Feel free to modify or extend this structure based on your project's needs.

### Inventory structure
I would strongly advice that the inventory you use should be placed ../ relative to the ansible repository.
This is good for reuse of ansible inventories.

The inventory could look like:
📦inventory  
 ┣ 📂dev  
 ┃ ┣ 📂group_vars  
 ┃ ┃ ┣ 📂all  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┃ ┗ 📂example_group  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┣ 📂host_vars  
 ┃ ┃ ┣ 📂example_host01  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┃ ┗ 📂example_host02  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┗ 📜inventory.ini  
 ┣ 📂prod  
 ┃ ┣ 📂group_vars  
 ┃ ┃ ┣ 📂all  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┃ ┗ 📂example_group  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┣ 📂host_vars  
 ┃ ┃ ┣ 📂example_host01  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┃ ┗ 📂example_host02  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┗ 📜inventory.ini  
 ┗ 📂test  
 ┃ ┣ 📂group_vars  
 ┃ ┃ ┣ 📂all  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┃ ┗ 📂example_group  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┣ 📂host_vars  
 ┃ ┃ ┣ 📂example_host01  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┃ ┗ 📂example_host02  
 ┃ ┃ ┃ ┣ 📜vars.yml  
 ┃ ┃ ┃ ┗ 📜vault.yml  
 ┃ ┗ 📜inventory.ini  

The `inventory` directory structure represents an Ansible inventory for different environments/stages (dev, prod, test). Here's an explanation of the directory structure:

- The `dev`, `prod`, and `test` directories represent different environments or stages.
- Each environment directory contains `group_vars` and `host_vars` directories for storing variables specific to groups or individual hosts.
- Within the `group_vars` and `host_vars` directories, there are further directories representing groups or hosts.
- Each group or host directory contains `vars.yml` and `vault.yml` files. `vars.yml` holds the variables specific to the group or host, while `vault.yml` is used to store sensitive variables encrypted with Ansible vault.
- Finally, each environment directory also contains an `inventory.ini` file, which defines the hosts and groups for that particular environment.

This directory structure allows you to organize your inventory variables and group/host-specific variables in a hierarchical manner, making it easier to manage and maintain your Ansible inventory.

Feel free to customize this structure based on your project's needs.



## Contributing

Contributions to improve this Ansible repository template are welcome. If you have any suggestions, bug reports, or feature requests, please open an issue or submit a pull request.

## License

This repository is licensed under the [MIT License](LICENSE). Feel free to use it as a starting point for your own Ansible projects.

## Acknowledgements

This template is inspired by best practices and common conventions for organizing Ansible projects.

Happy automating with Ansible!
