Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 2
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y openjdk-11-jdk tomcat9 maven
    systemctl enable --now tomcat9
  SHELL
end