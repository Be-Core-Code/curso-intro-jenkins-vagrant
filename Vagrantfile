# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/eoan64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provision "shell", inline: <<-SHELL
    wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | apt-key add -
    sh -c 'echo deb http://pkg.jenkins.io/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
    apt-get update
    apt-get install -y openjdk-8-jre 
    apt-get install -y jenkins
  SHELL
end
