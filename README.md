Keel on Kubernetes Ansible Role
===============================
This role will deploy the official Keel helm chart onto a k8s cluster (tested only in microk8s, due to specific storage class)

Requirements
------------
A functioning nicrok8s installation. You can use the following role to boot up such a cluster:
https://github.com/capitanh/microk8s_ansible_role

Role Variables
--------------
Tne variables required by this role are:
```yaml
# General
keel_port:                9300                        # External port of the k8s NodePort service
keel_user:                admin                       # Keel dashboard user name
keel_password:            admin                       # Keel dashobard user password (possibly kept in ansible vault)
```

Dependencies
------------
None

Example Playbook
----------------
Register the role in requirements.yml:
```yaml
    - src: capitanh.keelk8s_ansible_role
      name: keelk8s
```
Include it in your playbooks:
```yaml
    - hosts: servers
      roles:
      - keelk8s
```

License
-------
BSD
