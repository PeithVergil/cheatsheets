Vagrant
=======

### Adding boxes
    # Ubuntu 12.04
    vagrant box add precise32 http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-i386-vagrant-disk1.box
    vagrant box add precise64 http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-amd64-vagrant-disk1.box

    # Ubuntu 12.10
    vagrant box add quantal32 http://cloud-images.ubuntu.com/vagrant/quantal/current/quantal-server-cloudimg-i386-vagrant-disk1.box
    vagrant box add quantal64 http://cloud-images.ubuntu.com/vagrant/quantal/current/quantal-server-cloudimg-amd64-vagrant-disk1.box

### Initializing a new VM
`vagrant init precise32`

### Starting a VM
`vagrant up`

### Stopping a VM
`vagrant halt`

### Reloading a VM
`vagrant reload`

### Destroying a VM
`vagrant destroy`

### Listing boxes
`vagrant box list`

### Removing boxes
`vagrant box remove precise32 virtualbox`