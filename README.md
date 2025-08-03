# Gitlab playbooks

Ansible playbooks for managing resources in Gitlab.

## Prerequisites

Copy the example global vars file and populate it with your credentials.
```shell
cp global.vars.yml.example global.vars.yml
```

## Usage

For running a set of tasks you always need to pass on the `action` extra variable
to select the workflow for your intended changes.

### List projects

Example:
 ```shell
 ansible-playbook gitlabproject_manage.yml -e @global.vars.yml -e "action=projects_list"
 ```

 ### Create a project

**Extra variables**
| Variable name    | Required |
| ---------------- | -------- |
| project_name     |      yes |
| visibility       |      yes |
| merge_method     |      yes |
| project_template |       no |
| project_import   |       no |

Example:
 ```shell
ansible-playbook gitlabproject_manage.yml \
-e @global.vars.yml \
-e "project_name=foo" \
-e "visibility=private" \
-e "merge_method=ff" \
-e "action=project_create"
 ```


 ### Update a project

**Extra variables**
| Variable name    | Required |
| ---------------- | -------- |
| project_name     |      yes |
| visibility       |      yes |
| merge_method     |      yes |
| project_template |       no |
| project_import   |       no |

Example:
 ```shell
ansible-playbook gitlabproject_manage.yml \
-e @global.vars.yml \
-e "project_name=foo" \
-e "visibility=private" \
-e "merge_method=ff" \
-e "action=project_update"
 ```

 ### Delete a project

**Extra variables**
| Variable name    | Required |
| ---------------- | -------- |
| project_name     |      yes |

Example:
 ```shell
ansible-playbook gitlabproject_manage.yml \
-e @global.vars.yml \
-e "project_name=foo" \
-e "action=project_delete"
 ```
