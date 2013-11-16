# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  config.vm.network :hostonly, "172.16.0.10"
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["chef-repo/cookbooks"]
    chef.roles_path = ["chef-repo/roles"]
    chef.add_role "cache"
    chef.add_role "database"
    chef.add_recipe "dev_db"
    chef.json.merge!({:postgresql => {
        :password => {:postgres => "stagingpasswd" },
        :config => {:listen_addresses => "172.16.0.10" },
        :pg_hba => [
            {:type => "local", :db => "all", :user => "postgres", :addr => nil, :method => "ident"},
            {:type => "local", :db => "all", :user => "all", :addr => nil, :method => "ident"},
            {:type => "host", :db => "all", :user => "all", :addr => "172.16.0.10/32", :method => "md5"},
            {:type => "host", :db => "all", :user => "all", :addr => "172.16.0.1/32", :method => "md5"},
        ]
    } })
  end
end
