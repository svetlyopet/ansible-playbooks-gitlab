# Gitlab playbooks

Ansible playbooks for managing resources in Gitlab.

## Prerequisites

Copy the example global vars file and populate it with your credentials.
```shell
cp global.vars.yml.example global.vars.yml
```

## Usage

### List projects

 ```shell
 ansible-playbook gitlabproject_manage.yml --extra-vars @global.vars.yml --extra-vars "action=projects_list"
 ```