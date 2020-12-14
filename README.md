# Ansible Vault
* Used to encrypt variables and files to protect sensitive data.

## API Keys and Authentication
* AWS Command Line Interface - Interact with AWS services via the command line.
* Uses API Keys to connect - these are an area of vulnerability
* Secrets, keys, and environment variables all pose potential vulnerabilities therefore we must take precautions:
  * Do not share keys on open platforms such as GitHub
  * Do not keep keys close to code within files such as gitignore.
  * Environment variables should never be hard coded. They should be manually set.

### Considerations
1. Is it protected from going online?
2. Is it segregated from the code?
3. Is it encrypted?
4. Is it easy to share?

# Why Vault?
* Ansible has a module which works in conjunction with AWS CLI
* Vaults can be used to encrypt keys but they should still be kept offline. Examples of Vaults include:
  * Hashicorp Vault
  * Ansible Vault

# Using Ansible Vault
* Creating a vault file
```yaml
ansible-vault create file.yaml
```
  * Ask for a password and then confirmation before opening the file.
  * *Opens VIM, use `:wq` to escape.*

* Edit a file
```yaml
ansible-vault edit file.yaml
```

* View a file
```yaml
ansible-vault view file.yaml
```
## Creating an ec2 instance with Ansible



* Copy vars into Ansible directory
```yaml
sudo cp -r group_vars/ /etc/ansible/
```

* Run the instance playbook using:
```yaml
ansible-playbook creating_ec2.yml --ask-vault-pass --tags create_ec2
```
