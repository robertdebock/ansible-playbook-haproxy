Vagrant.configure("2") do |config|

  config.vm.box = "fedora/31-cloud-base"

  config.vm.define "frontend-01" do |one|
    config.vm.network :forwarded_port, host: 8080, guest: 80
    config.vm.network :forwarded_port, host: 8443, guest: 443
  end
  config.vm.define "backend-01"
  config.vm.define "backend-02"

  config.vm.provider "libvirt" do |lv|
    lv.memory = "1024"
   end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "dummy.yml"
    ansible.groups = {
      "frontends" => ["frontend-01"],
      "backends" => ["backend-01", "backend-02"]
    }
  end
end
