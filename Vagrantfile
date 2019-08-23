servers=[
  {
    :hostname => "webserver02",
    :ip => "192.168.20.12",
    :box => "centos/7",
    :ram => 256,
    :cpu => 1
  },
  {
    :hostname => "webserver03",
    :ip => "192.168.20.13",
    :box => "centos/7",
    :ram => 256,
    :cpu => 1
  },
  {
    :hostname => "webserver04",
    :ip => "192.168.20.14",
    :box => "centos/7",
    :ram => 256,
    :cpu => 1
  },
  {
    :hostname => "database10",
    :ip => "192.168.30.20",
    :box => "centos/7",
    :ram => 256,
    :cpu => 1
  },
  {
    :hostname => "database11",
    :ip => "192.168.30.21",
    :box => "centos/7",
    :ram => 256,
    :cpu => 1
  },
  {
    :hostname => "database12",
    :ip => "192.168.30.22",
    :box => "centos/7",
    :ram => 256,
    :cpu => 1
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