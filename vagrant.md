Vagrant
=======

### Adding boxes
    vagrant box add precise32 http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-vagrant-i386-disk1.box
    vagrant box add quantal32 http://cloud-images.ubuntu.com/quantal/current/quantal-server-cloudimg-vagrant-i386-disk1.box

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