Vagrant
=======

### Adding boxes
    vagrant box add precise32 http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-i386-vagrant-disk1.box
    vagrant box add quantal32 http://cloud-images.ubuntu.com/vagrant/quantal/current/quantal-server-cloudimg-i386-vagrant-disk1.box

### Adding boxes from VagrantCloud
`vagrant box add ubuntu/trusty32`

Check if the boxes are outdated:

```bash
vagrant box outdated
```

Update outdated boxes:

```bash
vagrant box update
```

### Initializing a new VM
`vagrant init precise32`

### Get VM status
`vagrant status`

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

Remove a box:

```bash
vagrant box remove ubuntu/trusty32 --provider virtualbox
```

Remove a box with a specific version:

```bash
vagrant box remove ubuntu/trusty32 --box-version 20151217.0.0
```

Repackage an existing box:

```sh
vagrant package --output example.box
```


Managing plugins
----------------------------------------

### Installing a plugin
`vagrant plugin install vagrant-vbguest`

### Uninstalling a plugin
`vagrant plugin uninstall vagrant-vbguest`

### List all installed plugins
`vagrant plugin list`

Update a plugin:

```bash
vagrant plugin update vagrant-vbguest
```


NFS Synced Folders
----------------------------------------

### Install on host machine
`sudo apt-get install nfs-kernel-server nfs-common portmap`

### Install on guest machine
`sudo apt-get install nfs-common portmap`

### Run the NFS daemon
`sudo /etc/init.d/nfs-kernel-server start`

### Setup Vagrant configuration file
    Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
      # NFS synced folders
      config.vm.synced_folder ".", "/vagrant", type: "nfs"

      # Private network
      config.vm.network :private_network, ip: "192.168.111.123"
    end


Troubleshooting
----------------------------------------

[Sync VirtualBox Guest Additions](http://kvz.io/blog/2013/01/16/vagrant-tip-keep-virtualbox-guest-additions-in-sync/)