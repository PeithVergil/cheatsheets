Vagrant
=======

### Adding boxes
    vagrant box add precise32 http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-i386-vagrant-disk1.box
    vagrant box add quantal32 http://cloud-images.ubuntu.com/vagrant/quantal/current/quantal-server-cloudimg-i386-vagrant-disk1.box

### Adding boxes from VagrantCloud
`vagrant box add ubuntu/trusty32`

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
`vagrant box remove precise32 virtualbox`


Managing plugins
----------------------------------------

### Installing a plugin
`vagrant plugin install vagrant-vbguest`

### Uninstalling a plugin
`vagrant plugin uninstall vagrant-vbguest`

### List all installed plugins
`vagrant plugin list`


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