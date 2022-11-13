Vagrant.configure("2") do |config|
  config.vm.define "terraform_oci_vm"
  config.vm.box = "ubuntu/focal64"
  config.vm.box_version = "20221018.0.0"
  config.vm.network "forwarded_port", guest: 8181, host: 8181
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 4
  end
  config.vm.synced_folder "./vagrant", "/vagrant"
  config.vm.provision "file", source: "./scripts", destination: "$HOME/scripts"
  config.vm.provision "shell", path: "./script.sh"
end