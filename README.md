ansible-hosts-example
=====================

This is a really simple example of how to test with Ansible.

Require packages
* Ansible
* Vagrant
* Ansible Lint
* Serverspec

If you have the above installed you should be able to do the below.
```
$ vagrant up
$ ./test_it
=> Linting Ansible Code
==> LINTING ./tasks/main.yml
==> LINTING ./test.yml
==> LINTING ./vars/test.yml
=> Run Ansible
==> default: Running provisioner: ansible...

PLAY [all] ********************************************************************

GATHERING FACTS ***************************************************************
ok: [default]

TASK: [ensure /etc/hosts] *****************************************************
ok: [default]

PLAY RECAP ********************************************************************
default                    : ok=2    changed=0    unreachable=0    failed=0

=> Verify Environment
/System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/bin/ruby -S rspec spec/default/httpd_spec.rb
...

Finished in 5.67 seconds
3 examples, 0 failures
=> SUCCESS
```
