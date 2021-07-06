# BoschTest

## Prerequisites
#### 1. The host you're going to perform the deployment from needs to have ansible installed.
#### 2. The host you are deploying to needs to have docker installed and the python interpreter for docker configured (pip/pip3 install docker).
#### 3. You need a user on the host you are deploying to with access to docker.
#### 4. Password authentication enabled on the host.
#
## Ansible configuration
#### - Set the host you are deploying to in the ansible-inventory.yml file in the <'hostname or ip address of host'> field.
#### - Set the password to connect via SSH in the same file in the <'ssh password'> field.
#### - Encrypt the ansible-inventory.yml file: ansible-vault encrypt ansible-inventory.yml
#
## How the app runs
#### The code is pulled and the yarn package manager runs against the specified packages.json file.
#### There are 2 containers running on the host (app and mysql), only the "app" one exposed on port 80 (containter port 3000). The inventory also says that the port is 80.
#### The mysql container has a mapped volume created priorly, so data is persisted on the VM disk.
#### The app can be accessed via HTTP.