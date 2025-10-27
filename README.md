Setup requirements
=========

```
  pyenv install 3.12.0
  pyenv virtualenv 3.12.0 ansible-env
  pyenv activate ansible-env
  pip install --upgrade pip
  pip install -r requirements.txt
```

Role Name
=========

Setup open-ssh server with basic os-hardening.

Role Variables
--------------

You must specify the authorized user for incomming ssh connections.

```
  host_authorized_users:
    - ansible
    - foo
```


Example
----------------

```
  - hosts: webservers
    tasks:
      - name: "Include sshd role"
        ansible.builtin.include_role:
          name: "jimtesson.sshd_setup"
          vars:
            host_authorized_users:
              - ansible
              - foo

```


Tests
----------------

```
  # create the instance
  molecule create

  # apply the playbook
  molecule converge

  # test the playbook
  molecule verify

  # destroy the instance
  molecule destroy  
```

License
-------

BSD
