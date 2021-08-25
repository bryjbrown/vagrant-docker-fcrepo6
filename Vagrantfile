Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/hirsute64"
  config.vm.provision :shell, 
  path: "build.sh",
  keep_color: true
  config.vm.synced_folder ".", "/sync", :mount_options => ["dmode=777","fmode=666"]
  config.vm.network :forwarded_port, host: 9999, guest: 80
  config.vbguest.auto_update = false
  config.vm.define 'vagrant-docker-fcrepo6' do |t|
    config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 4096]
    end
  end
end
