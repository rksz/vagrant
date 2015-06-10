Vagrant.configure(2) do |config|
  config.vm.box = "chef/centos-6.6"

  #========================================
  # local node
  #========================================
  config.vm.define :"local-node-01" do |node|
    node.vm.network :private_network, ip: '192.168.33.22'
    node.vm.provision "shell", inline: <<-EOT
      setenforce 0
      sed -ri 's/SELINUX=.*/SELINUX=disabled/' /etc/selinux/config
    EOT

#    node.vm.synced_folder "../", "/vagrant-shared", \
#      :create        => true, \
#      :owner         => 'vagrant', \
#      :group         => 'vagrant', \
#      :mount_options => ['dmode=777,fmode=777']
#    node.vm.provider :virtualbox do |vb|
#      vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
#      vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
#    end
  end
end
