# vagrant-vb

starting point: \
https://developer.hashicorp.com/vagrant/tutorials/getting-started

```
vagrant init centos/8
vagrant up
vagrant ssh
vagrant ssh-config
vagrant halt
vagrant suspend
vagrant resume
vagrant reload
vagrant destroy
vagrant status
vagrant package --output mybox.box
vagrant provision
vagrant plugin 

vagrant box add ubuntu/focal64
vagrant box list
vagrant box outdated
vagrant box update ubuntu/focal64
vagrant box repackage ubuntu/focal64 --name my-new-box
vagrant box prune
vagrant box remove ubuntu/focal64

vboxmanage list vms
vboxmanage list runningvms
```
