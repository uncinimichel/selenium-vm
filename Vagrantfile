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

  # Configure Selenium Grid
    config.vm.define :'selenium-grid' do |selenium_grid|
    selenium_grid.vm.network :private_network, ip: "10.1.1.69"
    selenium_grid.vm.network "forwarded_port", guest: 3389, host: 3390 # RPD port
    selenium_grid.vm.hostname = "selenium.local.vm"
    selenium_grid.vm.provider :virtualbox do |vb|
      vb.customize [
                    "modifyvm", :id,
                    "--name", "selenium-grid",
                    "--memory", "512",
                    "--cpus", 1,
                   ]
    end
    selenium_grid.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

    selenium_grid.vm.provision :chef_solo do |chef_solo|
      chef_solo.cookbooks_path = chef_solo_cookbook_path
      chef_solo.add_recipe 'selenium-grid'
    end
  end

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
    end
  end
end
