Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
  config.vm.define "kafkarh7" do |kafkarh7|
#   kafkarh7.vm.box = "RHEL7.5.1_baserepo"
    kafkarh7.vm.box = "RH7.5_baserepo"
#   kafkarh7.vm.box = "generic/rhel7"
    #kafkarh7.vm.box = "iamseth/rhel-7.3"
    #kafkarh7.vm.box = "javier-lopez/rhel-7.4"
    #kafkarh7.vm.box = "xianlin/rhel-7.4"
    kafkarh7.vm.hostname = "kafkarh7"
    kafkarh7.vm.network "private_network", ip: "192.168.60.199"
    kafkarh7.vm.provision "shell", :inline => "sudo echo '192.168.60.199 kafkarh7.local kafkarh7' >> /etc/hosts"

    kafkarh7.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_kafka.yml"
      ansible.inventory_path = "vagrant_hosts"
      #ansible.tags = ansible_tags
      #ansible.verbose = ansible_verbosity
      #ansible.extra_vars = ansible_extra_vars
      #ansible.limit = ansible_limit
    end
  end
end
