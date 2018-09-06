Vagrant.configure("2") do |config|
  
  # VM名
  config.vm.define :www do |c|
    define_machine_name c, "vagrant_python-flask"
  end

  # Ubuntu 18.04 LTS
  config.vm.box = "bento/ubuntu-18.04"

  config.vm.network "private_network", ip: "192.168.33.90"
  config.vm.synced_folder "./", "/vagrant"

  # docker の設定
  config.vm.provision :docker, run: "always"

  # doker-composeの設定
  config.vm.provision :docker_compose,
    yml: "/vagrant/docker-compose.yml",
    compose_version: "1.22.0",
    run: "always"

end

def define_machine_name(c, name)
  c.vm.provider :virtualbox do |vbox|
    vbox.name = name
  end
end
