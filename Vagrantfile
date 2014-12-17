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
  config.omnibus.chef_version = '11.16.4'

  nodes = [
    {
      :private_ip => '10.1.1.3',
      :rdp_port => 3391,
      :selenium_port => 6001,
      :name => 'node1'
    },
    {
      :private_ip => '10.1.1.4',
      :rdp_port => 3392,
      :selenium_port => 6002,
      :name => 'node2'
    },
    {
      :private_ip => '10.1.1.5',
      :rdp_port => 3393,
      :selenium_port => 6003,
      :name => 'node3'
    },
    {
      :private_ip => '10.1.1.6',
      :rdp_port => 3394,
      :selenium_port => 6004,
      :name => 'node4'
    },
    {
      :private_ip => '10.1.1.7',
      :rdp_port => 3395,
      :selenium_port => 6005,
      :name => 'node5'
    },
    {
      :private_ip => '10.1.1.8',
      :rdp_port => 3396,
      :selenium_port => 6006,
      :name => 'node6'
    },
    {
      :private_ip => '10.1.1.9',
      :rdp_port => 3397,
      :selenium_port => 6007,
      :name => 'node7'
    },
    {
      :private_ip => '10.1.1.10',
      :rdp_port => 3398,
      :selenium_port => 6008,
      :name => 'node8'
    }
  ]

  (nodes).each do |node|
    config.vm.define "#{node[:name]}" do |grid_node|
      grid_node.vm.network :private_network, ip: "#{node[:private_ip]}"
      grid_node.vm.network "forwarded_port", guest: 3389, host: node[:rdp_port]
      grid_node.vm.network "forwarded_port", guest: node[:selenium_port], host: node[:selenium_port]
      grid_node.vm.hostname = "node.selenium.vm"
      grid_node.vm.provider :virtualbox do |vb|
        vb.customize [
                      "modifyvm", :id,
                      "--name", "#{node[:name]}",
                      "--memory", "512",
                      "--cpus", 1,
                     ]
      end
      grid_node.vm.provision "shell", inline: "echo '#{node[:selenium_port]}' > /.selenium-port"
      grid_node.vm.provision :shell, :inline => CHEF_CLIENT_INSTALL

      grid_node.vm.provision :chef_solo do |chef_solo|
        chef_solo.cookbooks_path = chef_solo_cookbook_path
        chef_solo.add_recipe 'selenium-grid::node'
        chef_solo.add_recipe 'chef-timezone::default'
      end
    end
  end
end
