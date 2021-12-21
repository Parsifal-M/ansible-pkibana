Role Name
=========

Installs Kibana on the target machine.

Requirements
------------
`Ansible` and below is the ansible galaxy installation command:

```
ansible-galaxy install parsifal_m.ansible_pkibana
```

Role Variables
--------------

Kibana Version to Install
```
kibversion: "7.x"
```
Package Name
```
kibpackage: kibana
```
Package can be `present`, `absent` or `latest`.
```
kibpackage_state: present
```

This is the kibana.yml file template

```
kibconfig_template: kibana.yml.j2
```

This is where to put the kibana.yml file

```
kibconfig_file_path: /etc/kibana/kibana.yml
```

To enable Kibana service

```
kibservice_state: started

```
To make sure its enabled on boot

```
kibservice_enabled: true
```

Basic HTTP authentication settings

```
kibelasticsearch_username: username
kibelasticsearch_password: hunter2
```

IP and Port settings, and optional display name.

```
kibserver_port: 5601
kibserver_host: 0.0.0.0
kibserver_name: test-kibana
```

The URL of the Elasticsearch instance to use for all your queries

```
kibelastic_search_url: http://localhost:9200
```

Dependencies
------------

Currently, none.

Example Playbook
----------------


    - hosts: servers
      roles:
         - parsifal_m.ansible_pkibana

License
-------

BSD
