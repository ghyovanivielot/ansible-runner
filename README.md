# Windows Server Automation with Ansible

A comprehensive Ansible automation suite for Windows Server management, demonstrating enterprise-level infrastructure automation capabilities.

## Overview

This project provides production-ready Ansible playbooks for automating Windows Server configuration, application deployment, and system management tasks. It showcases best practices for infrastructure as code, configuration management, and DevOps automation in Windows environments.

## Features

- Complete Windows Server configuration management
- Automated web application deployment with rollback capabilities
- User and service account management
- Registry configuration and scheduled task automation
- Multi-environment inventory support
- Security-focused credential management with Ansible Vault
- Comprehensive error handling and recovery mechanisms
- Deployment verification and health checks

## Prerequisites

- Ansible 2.15 or higher
- Python 3.9 or higher
- Windows Server 2016+ with WinRM enabled
- PowerShell 5.1 or higher

## Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/ghyovanivielot/ansible-runner.git
   cd ansible-runner
   ```

2. Set up Python virtual environment:
   ```bash
   python3 -m venv ansible-venv
   source ansible-venv/bin/activate
   pip install ansible pywinrm
   ```

3. Configure inventory:
   ```bash
   cp inventory/production.example inventory/production
   # Edit inventory/production with your Windows servers
   ```

4. Run the demonstration playbook:
   ```bash
   # macOS users may need this environment variable
   export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
   
   ansible-playbook playbooks/interview-demo.yml -i inventory/production
   ```

## Project Structure

```
├── playbooks/
│   ├── interview-demo.yml          # Comprehensive demonstration playbook
│   ├── deploy-webapp.yml           # Production web application deployment
│   ├── windows-server-setup.yml    # Complete server configuration
│   ├── verify-changes.yml          # Deployment verification
│   └── ...                         # Additional automation playbooks
├── inventory/
│   ├── production.example          # Template inventory file
│   └── production                  # Production environment (not in repo)
├── group_vars/
│   └── windows/
│       ├── main.yml               # Configuration variables
│       └── vault.yml.example      # Template for encrypted secrets
├── templates/
│   └── web.config.j2              # Application configuration template
└── roles/                         # Ansible roles directory structure
```

## Key Playbooks

### Interview Demo (interview-demo.yml)
Demonstrates core Windows automation capabilities including:
- System information gathering and validation
- User account and service management
- Directory structure creation and file deployment
- Registry configuration management
- Scheduled task automation
- Service state management
- Comprehensive error handling

### Web Application Deployment (deploy-webapp.yml)
Production-ready deployment workflow featuring:
- Automated backup and rollback mechanisms
- Security-focused service account creation
- IIS configuration and website management
- Application health checks and verification
- Comprehensive logging and reporting

## Security Implementation

- Ansible Vault integration for sensitive data encryption
- Service accounts configured with least-privilege access
- No hardcoded credentials in playbooks
- Secure WinRM configuration requirements
- Input validation and sanitization

## Verification and Testing

Execute the verification playbook to validate all deployed components:

```bash
ansible-playbook playbooks/verify-changes.yml -i inventory/production
```

This playbook validates:
- Directory structures and file deployments
- User accounts and permissions
- Registry settings and configurations
- Scheduled tasks and service states
- Application functionality and accessibility

## Skills Demonstrated

- **Infrastructure as Code**: Declarative server configuration management
- **Configuration Management**: Consistent, repeatable deployments across environments
- **Error Handling**: Robust failure recovery and automatic rollback mechanisms
- **Security Best Practices**: Encrypted credential management and secure authentication
- **Multi-Environment Management**: Scalable inventory and variable organization
- **Windows Administration**: PowerShell integration, IIS management, registry operations
- **DevOps Practices**: Automated testing, verification, and deployment workflows

## Advanced Usage

### Encrypting Sensitive Data
```bash
ansible-vault encrypt group_vars/windows/vault.yml
```

### Multi-Environment Deployments
```bash
# Development environment
ansible-playbook playbooks/deploy-webapp.yml -i inventory/development

# Production environment
ansible-playbook playbooks/deploy-webapp.yml -i inventory/production
```

### Variable Overrides
```bash
ansible-playbook playbooks/interview-demo.yml -i inventory/production -e "app_version=2.0.0"
```

## Results and Impact

This automation suite enables:
- Parallel deployment across multiple Windows servers
- Zero-downtime deployments with automatic rollback capability
- Consistent configuration management across environments
- Significant reduction in deployment time and manual errors
- Elimination of configuration drift through automated enforcement

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Author

**Ghyovani Vielot**
- GitHub: [@ghyovanivielot](https://github.com/ghyovanivielot)
- LinkedIn: [Connect with me](https://www.linkedin.com/in/ghyovani-vielot/)
---

This project demonstrates enterprise-level Windows Server automation capabilities using Ansible, showcasing expertise in infrastructure as code, configuration management, and DevOps best practices.
