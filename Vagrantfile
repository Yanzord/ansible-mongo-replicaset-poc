# -*- mode: ruby -*-
# vi: set ft=ruby :

servers=[
  {
    :hostname => "node-one",
    :ip => "192.168.100.10",
    :box => "ubuntu/bionic64",
    :ram => 1024,
    :cpu => 2
  },
  {
    :hostname => "node-two",
    :ip => "192.168.100.11",
    :box => "ubuntu/bionic64",
    :ram => 1024,
    :cpu => 2
  },
  {
    :hostname => "node-three",
    :ip => "192.168.100.12",
    :box => "ubuntu/bionic64",
    :ram => 1024,
    :cpu => 2
  }
]

Vagrant.configure(2) do |config|
    servers.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = machine[:box]
            node.vm.hostname = machine[:hostname]
            node.vm.network "private_network", ip: machine[:ip]
            node.vm.provider "virtualbox" do |vb|
                vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
           end
       end 
   end
end