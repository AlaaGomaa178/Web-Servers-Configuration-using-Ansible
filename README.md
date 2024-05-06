---

# Web Servers Configuration using Ansible

## Overview

This Ansible project automates the configuration of web servers by setting up Jenkins and Nginx with SSL certificates. It streamlines the process of deploying Jenkins for continuous integration and managing reverse proxying with Nginx for secure access.

## Project Structure

The project directory is structured as follows:

- **jenkins-role/**: Ansible role for Jenkins and Nginx configuration.
  - **defaults/**: Default variable definitions.
  - **handlers/**: Handler tasks for service management.
    - **main.yml**: Handler tasks for restarting services.
  - **meta/**: Metadata about the role.
  - **tasks/**: Main tasks for installation and configuration.
    - **main.yml**: Tasks for installing OpenJDK, adding repositories, installing Jenkins, setting up Nginx, generating SSL certificates, and deploying configurations.
  - **templates/**: Jinja2 templates for Nginx configuration.
    - **jenkins.conf.j2**: Template for Nginx reverse proxy configuration.
  - **tests/**: Test-related files.
    - **test.yml**: Playbook for testing the jenkins-role.

- **MyAnsKP.pem**: Private key file (not included in the repository).

- **install.yml**: Main playbook for installing Jenkins and Nexus.

- **inventory**: Inventory file containing target host(s) IP addresses.

## Usage

### Prerequisites

Before running the playbook, ensure the following prerequisites are met:

- Ansible is installed on your local machine.
- Target host(s) are reachable from your local machine.
- Replace `MyAnsKP.pem` with your actual private key for SSH authentication.

### Installation Steps

1. Clone the repository:

   ```shell
   git clone https://github.com/yourusername/Web-Servers-Configuration-using-Ansible.git
   ```

2. Navigate to the project directory:

   ```shell
   cd Web-Servers-Configuration-using-Ansible
   ```

3. Edit the `inventory` file to specify your target host(s) IP addresses or hostnames.

4. Run the main playbook to install Jenkins and Nginx:

   ```shell
   ansible-playbook install.yml -i inventory --private-key=MyAnsKP.pem
   ```

5. Access Jenkins via your browser at `https://jenkins.yourdomain.com`.

## Contributing

Contributions are welcome! If you want to contribute to this project, follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/new-feature`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push your changes to the branch (`git push origin feature/new-feature`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or feedback, feel free to contact me at alaa.gomaa178@gmail.com(mailto:alaa.gomaa178@gmail.com).

---
