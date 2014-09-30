chef_solo_cookbook_path = ["cookbooks", "site-cookbooks"]
CHEF_CLIENT_INSTALL = <<-EOF
#!/bin/sh
dpkg -l curl|grep -q ^ii || {
  apt-get update
  apt-get install -y curl
}

test -d /opt/chef || {
  echo "Installing chef-client via omnibus"
  curl -L -s https://www.opscode.com/chef/install.sh | bash
}
EOF

Vagrant::configure("2") do |config|
  config.vm.box = "Ubuntu Precise 32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"

    # Configure Selenium Node
  config.vm.define :'node1' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.3"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3391 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
    grid_node.vm.provider :virtualbox do |vb|
      vb.customize [
                    "modifyvm", :id,
                    "--name", "node1",
                    "--memory", "512",
                    "--cpus", 1,
                   ]
    end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

    # Configure Selenium Node
  config.vm.define :'node2' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.4"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3392 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
        grid_node.vm.provider :virtualbox do |vb|
          vb.customize [
                        "modifyvm", :id,
                        "--name", "node2",
                        "--memory", "512",
                        "--cpus", 1,
                       ]
        end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

    # Configure Selenium Node
  config.vm.define :'node3' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.5"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3393 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
    grid_node.vm.provider :virtualbox do |vb|
        vb.customize [
                      "modifyvm", :id,
                      "--name", "node3",
                      "--memory", "512",
                      "--cpus", 1,
                     ]
    end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

    # Configure Selenium Node
  config.vm.define :'node4' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.6"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3394 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
    grid_node.vm.provider :virtualbox do |vb|
      vb.customize [
                    "modifyvm", :id,
                    "--name", "node4",
                    "--memory", "512",
                    "--cpus", 1,
                   ]
    end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

    # Configure Selenium Node
  config.vm.define :'node5' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.7"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3395 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
    grid_node.vm.provider :virtualbox do |vb|
      vb.customize [
                    "modifyvm", :id,
                    "--name", "node5",
                    "--memory", "512",
                    "--cpus", 1,
                   ]
    end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

    # Configure Selenium Node
  config.vm.define :'node6' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.8"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3396 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
    grid_node.vm.provider :virtualbox do |vb|
      vb.customize [
                    "modifyvm", :id,
                    "--name", "node6",
                    "--memory", "512",
                    "--cpus", 1,
                   ]
    end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

    # Configure Selenium Node
  config.vm.define :'node7' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.9"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3397 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
    grid_node.vm.provider :virtualbox do |vb|
      vb.customize [
                    "modifyvm", :id,
                    "--name", "node7",
                    "--memory", "512",
                    "--cpus", 1,
                   ]
    end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

    # Configure Selenium Node
  config.vm.define :'node8' do |grid_node|
    grid_node.vm.network :private_network, ip: "10.1.1.10"
    grid_node.vm.network "forwarded_port", guest: 3389, host: 3398 # RPD port
    grid_node.vm.hostname = "node.selenium.vm"
    grid_node.vm.provider :virtualbox do |vb|
      vb.customize [
                    "modifyvm", :id,
                    "--name", "node8",
                    "--memory", "512",
                    "--cpus", 1,
                   ]
    end
    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    grid_node.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid::node'
      chef_solo.add_recipe 'chef-timezone::default'
    end
  end

#    # Configure Selenium Node
#  config.vm.define :'node9' do |grid_node|
#    grid_node.vm.network :private_network, ip: "10.1.1.11"
#    grid_node.vm.network "forwarded_port", guest: 3389, host: 3399 # RPD port
#    grid_node.vm.hostname = "node.selenium.vm"
#    grid_node.vm.provider :virtualbox do |vb|
#      vb.customize [
#                    "modifyvm", :id,
#                    "--name", "node9",
#                    "--memory", "512",
#                    "--cpus", 1,
#                   ]
#    end
#    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL
#
#    grid_node.vm.provision :chef_solo do |chef_solo|
#      chef_solo.cookbooks_path = chef_solo_cookbook_path
#      chef_solo.add_recipe 'selenium-grid::node'
#      chef_solo.add_recipe 'chef-timezone::default'
#    end
#  end

#    # Configure Selenium Node
#  config.vm.define :'node10' do |grid_node|
#    grid_node.vm.network :private_network, ip: "10.1.1.12"
#    grid_node.vm.network "forwarded_port", guest: 3389, host: 3400 # RPD port
#    grid_node.vm.hostname = "node.selenium.vm"
#    grid_node.vm.provider :virtualbox do |vb|
#      vb.customize [
#                    "modifyvm", :id,
#                    "--name", "node10",
#                    "--memory", "512",
#                    "--cpus", 1,
#                   ]
#    end
#    grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL
#
#    grid_node.vm.provision :chef_solo do |chef_solo|
#      chef_solo.cookbooks_path = chef_solo_cookbook_path
#      chef_solo.add_recipe 'selenium-grid::node'
#      chef_solo.add_recipe 'chef-timezone::default'
#    end
#  end
end
