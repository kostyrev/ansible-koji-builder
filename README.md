koji-builder
=========

This role configures koji builder.

This is one of the koji- roles which configures the whole koji stack.

Roles are:

 * [koji-ca](https://galaxy.ansible.com/kostyrevaa/koji-ca)
 * [koji-db](https://galaxy.ansible.com/kostyrevaa/koji-db)
 * [koji-client](https://galaxy.ansible.com/kostyrevaa/koji-client)
 * [koji-hub](https://galaxy.ansible.com/kostyrevaa/koji-hub)
 * [koji-web](https://galaxy.ansible.com/kostyrevaa/koji-web)
 * [koji-kojira](https://galaxy.ansible.com/kostyrevaa/koji-kojira)
 * [koji-builder](https://galaxy.ansible.com/kostyrevaa/koji-builder)

For example of all-in-one setup go to https://github.com/kostyrevaa/ansible-koji-infra

Role Variables
--------------

There are some variables in the default/main.yml which can (or needs to) be changed/overriden:

* `koji_builder_hub_server`: This is the url of koji hub. Default uses hostvars discover.

* `koji_builder_workdir`: This is workdir of the builder. Default is /tmp/koji.

* `koji_builder_topurl`: This is the url of kojifiles. Default uses hostvars discover.

* `koji_builder_pem`: This is the client certificate of this builder in pem format. Default is /etc/pki/koji/pems/{{ ansible_fqdn }}.pem.

* `koji_builder_ca`: This is the certificate of the CA that issued the client certificate. Default is /etc/pki/koji/koji_ca_cert.crt.

* `koji_builder_serverca`: This is the certificate of the CA that issued the HTTP server certificate. Default is /etc/pki/koji/koji_ca_cert.crt.

* `koji_builder_patch_crearepo`: Weather or not patch createrepo python code. Default is false. See https://bugzilla.redhat.com/show_bug.cgi?id=1091708


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: koji_builder
      roles:
         - koji-builder


License
-------

GPLv3

Author Information
------------------

Send your suggestions and pull requests to https://github.com/kostyrevaa/ansible-koji-builder.  
When send PR make sure your changes are backward-compatible.  
You may test your changes to role with https://github.com/kostyrevaa/ansible-koji-infra
