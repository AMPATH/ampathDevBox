required_plugins = %w( vagrant-env vagrant-fsnotify )
required_plugins.each do |plugin|
  unless Vagrant.has_plugin?(plugin)
    system("vagrant plugin install #{plugin}", :chdir=>"/tmp") || exit!
  end
end
Vagrant.configure("2") do |config|
  config.vm.box = "ampath"
  config.vm.box_url = "file:////home/achachiez/Code/Vagrant/Boxes/ampathDevBox.box"
  config.env.enable # Enable vagrant-env(.env)
  #config.vm.box_version = ".+"
  config.vm.synced_folder ENV['WORKSPACE_DIR'], "/home/vagrant/workspace" , create: true
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 4200, host: 4200
  config.vm.network "forwarded_port", guest: 8002, host: 8002
  config.vm.network "forwarded_port", guest: 8080, host: 8089
  config.vm.network "forwarded_port", guest: 3306, host: 3309
  config.vm.network "forwarded_port", guest: 5986, host: 5986
  config.vm.network "forwarded_port", guest: 5984, host: 5984
  # config.ssh.username = 'vagrant'
  # config.ssh.password = 'vagrant'
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end

end
