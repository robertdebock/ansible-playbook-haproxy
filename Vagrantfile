Vagrant.configure("2") do |config|

  config.vm.box = "fedora/31-cloud-base"

  config.vm.define "frontend-01"
  config.vm.define "frontend-02"
  config.vm.define "backend-01"
  config.vm.define "backend-02"

  config.vm.provider "libvirt" do |lv|
    lv.memory = "1024"
   end

  config.vm.provision "ansible" do |ansible|
    # ansible.playbook = "dummy.yml"
    ansible.groups = {
      "frontends" => ["frontend-01","frontend-02"],
      "backends" => ["backend-01", "backend-02"]
    }
  end
end
