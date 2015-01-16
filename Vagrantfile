##################################################
# Generated by phansible.com
##################################################

Vagrant.configure("2") do |config|

    config.vm.provider :virtualbox do |v|
        v.name = "Default"
        v.customize ["modifyvm", :id, "--memory", 1024]
    end

    config.vm.box = "ubuntu/trusty64"
    
    config.vm.network :private_network, ip: "192.168.33.99"
    config.ssh.forward_agent = true

    #############################################################
    # Ansible provisioning (you need to have ansible installed)
    #############################################################

    
    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/playbook.yml"
        ansible.inventory_path = "ansible/inventories/dev"
        ansible.limit = 'all'
    end
    
    config.vm.synced_folder "./", "/vagrant"
end
