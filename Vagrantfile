Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.network "forwarded_port", guest: 8888, host: 18888
  config.vm.network "forwarded_port", guest: 9160, host: 19160
  config.vm.network "forwarded_port", guest: 9042, host: 19042

  config.vm.provider "virtualbox" do |v|
    v.name   = "dse"
    v.memory = "4096"
  end
#  config.vm.define "dse" do |dse|
#  end
  config.vm.provision "shell",
    :path => "vagrant_specs.sh",
    :upload_path => "/home/ubuntu/specs",
    # change role name below
    :args => "--install ansible-dse"
end

