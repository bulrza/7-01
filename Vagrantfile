
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  #config.vm.provider = 'virtualbox'

  config.vm.define "net1" do | p |
   p.vm.box = 'centos/7'
   p.vm.host_name = "net1"
   #p.vm.network  "public_network", bridge: "Realtek PCIe GbE Family Controller"
   p.vm.network "private_network", ip: "10.2.2.41"
       p.vm.provider :virtualbox do |res|

          res.customize ["modifyvm", :id, "--cpus", "1"]
          res.customize ["modifyvm", :id, "--memory", "2000"]
       end

  end

  config.vm.define "net2" do | b |
   b.vm.box= 'centos/7'
   b.vm.host_name = "net2"

   #b.vm.network  "public_network", bridge: "Realtek PCIe GbE Family Controller"
   b.vm.network "private_network", ip: "10.2.2.42"
      b.vm.provider :virtualbox do |res|

        res.customize ["modifyvm", :id, "--cpus", "1"]
        res.customize ["modifyvm", :id, "--memory", "2000"]
      end

  end

  config.vm.define "ansible" do | c |
   c.vm.box= 'ubuntu/focal64'
   c.vm.host_name = "ansible"

   c.vm.network  "public_network", bridge: "Realtek PCIe GbE Family Controller"
   c.vm.network "private_network", ip: "10.2.2.40"
      c.vm.provider :virtualbox do |res|

        res.customize ["modifyvm", :id, "--cpus", "2"]
        res.customize ["modifyvm", :id, "--memory", "2000"]
      end

  end
end
