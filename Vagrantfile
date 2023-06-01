Vagrant.configure("2") do |config|
    #config.vm.box = "generic/ubuntu1804"
    config.vm.box = "generic/ubuntu2204"

    config.vm.hostname = 'ubuntu'

    # Prevent SharedFoldersEnableSymlinksCreate errors
    #config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.synced_folder "./synced_folder", "/vagrant", create: true

    config.vm.provision "ansible" do |ansible|
    ### https://www.vagrantup.com/docs/provisioning/ansible_common.html
      ansible.compatibility_mode = "2.0"
      ansible.become = "true"
      ansible.become_user = "root"
#     ansible.config_file = "provisioning/ansible.cfg"
      ansible.playbook = "provisioning/playbook.yml"
    end
end
