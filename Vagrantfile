Vagrant.configure("2") do |config|
  config.vm.box = "mrdeff/bitrixvm7"
  config.vm.box_check_update = false
  config.vm.hostname = "bitrixvm7"
  #config.vm.network "forwarded_port", guest: 80, host: 8181, auto_correct: true
  #config.vm.network "forwarded_port", guest: 8888, host: 8888, auto_correct: true
  #config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network "public_network"
  config.vm.boot_timeout = 300
  config.vm.synced_folder "www", "/home/bitrix/www/", owner: "bitrix", group: "bitrix", mount_options: ["dmode=775,fmode=664"]
  config.vm.synced_folder "tmp", "/home/bitrix/tmp/", owner: "bitrix", group: "bitrix", mount_options: ["dmode=775,fmode=664"]

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = 1024
    vb.cpus = 1
  end
   config.vm.provision "shell", inline: <<-SHELL
	mkdir /home/bitrix/tmp/
	yum -y update
	mysql -u root -pvagrant -e "create database main"; 
	mysql -uroot -pvagrant main < /home/bitrix/tmp/mysql.sql || exit 1
	ifconfig
   SHELL
end
