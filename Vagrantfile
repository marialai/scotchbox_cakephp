# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    # fix UTF-8 bug in scotch/box
    config.vm.provision "shell", inline: "echo LC_ALL=en_US.UTF-8 | sudo tee --append /etc/environment"
    config.vm.provision "shell", inline: "echo LANG=en_US.UTF-8 | sudo tee --append /etc/environment"
    
    # update composer
    config.vm.provision "shell", inline: "composer self-update"

    # install cakephp empty project
    config.vm.provision "shell", inline: "composer create-project --prefer-dist cakephp/cakephp=2.8.5 /var/www/public"
    
    # copy app.php with scotch/box MySQL settings to config
    config.vm.provision "file", source: "app.php", destination: "/var/www/public/config/app.php"

    # copy adminer.php to webroot
    config.vm.provision "file", source: "adminer.php", destination: "/var/www/public/app/webroot/adminer.php"

    # default config
    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "scotchbox"
    config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]
    
    # Optional NFS. Make sure to remove other synced_folder line too
    #config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }

end
