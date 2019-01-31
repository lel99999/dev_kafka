Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
  config.vm.define "kafkaRH7" do |kafkaRH7|
#   kafkaRH7.vm.box = "RHEL7.5.1_baserepo"
    kafkaRH7.vm.box = "RH7.5_baserepo"
#   kafkaRH7.vm.box = "generic/rhel7"
    #kafkaRH7.vm.box = "iamseth/rhel-7.3"
    #kafkaRH7.vm.box = "javier-lopez/rhel-7.4"
    #kafkaRH7.vm.box = "xianlin/rhel-7.4"
    kafkaRH7.vm.hostname = "kafkaRH7"
    kafkaRH7.vm.network "private_network", ip: "192.168.60.199"
    kafkaRH7.vm.provision "shell", :inline => "sudo echo '192.168.60.199 kafkaRH7.local kafkaRH7' >> /etc/hosts"

    kafkaRH7.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_kafka.yml"
      ansible.inventory_path = "vagrant_hosts"
      #ansible.tags = ansible_tags
      #ansible.verbose = ansible_verbosity
      #ansible.extra_vars = ansible_extra_vars
      #ansible.limit = ansible_limit
    end
  end
end
