# -*- mode: ruby -*-
# vi: set ft=ruby :

# Alerta para instalação e configuração do plugin vbguest para atualização do
# VirtualBox Guest Additions
unless Vagrant.has_plugin?("vagrant-vbguest")
  warn "\n\n**********************************************************\n\n"+
       "                          ATENÇAO !!!                        \n\n"+
       "Não foi localizado o plugin vagrant-vbguest na máquina host. \n\n"+
       "Recomendamos seu uso para evitar incompatibilidades de versões \n"+
       "entre o Virtualbox e VBGuest Addition, impactando o          \n"+
       "compartilhamento de pastas. \n\n"+
       "Para solucionar o problema, execute o seguinte comando no \n"+
       "diretório raiz do projeto. \n\n"+
       "> vagrant plugin install vagrant-vbguest                     \n"+
       "\n********************************************************** \n\n"+
       " Pressione ENTER para continuar ou (Ctrl + C) para finalizar ... \n\n"

  $stdin.gets; puts "\n"
end

Vagrant.configure(2) do |config|
  ## Instalação de plugin para configuração automática do disco
  required_plugins = %w( vagrant-vbguest vagrant-disksize vagrant-env)
  _retry = false
  required_plugins.each do |plugin|
    unless Vagrant.has_plugin? plugin
      system "vagrant plugin install #{plugin}"
      _retry=true
    end
  end

  if (_retry)
    exec "vagrant " + ARGV.join(' ')
  end
  
  # Box do vagrant contendo o ambiente de desenvolvimento do SEI
  config.vm.box = "bento/ubuntu-20.04"
#   config.vm.box = "hashicorp/precise64"
#   config.vm.box = "processoeletronico/sei-3.1"
#   config.vm.box = "centos/7"

  config.env.enable # Enable vagrant-env(.env)

  config.disksize.size = "100GB"
  config.vbguest.auto_update = true
  config.vbguest.no_remote = false
  config.vbguest.iso_mount_point = "/media"
  config.vbguest.installer_options = { allow_kernel_upgrade: true }

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", ENV['HOST_MEMORY'], "--usb", "off", "--audio", "none"]
  end
  
  # Configuração do diretório local onde deverá estar disponibilizado os códigos-fontes do SEI (sei, sip, infra_php, infra_css, infra_js)
  config.vm.synced_folder ENV['DISCODOCKER_HOME'], "/home/docker/discoDocker", mount_options: ["dmode=777", "fmode=777"]
  config.vm.synced_folder ".", "/home/docker/discoDocker/docker", mount_options: ["dmode=777", "fmode=777"]


  # Configuração do redirecionamento entre Máquina Virtual e Host
  config.vm.network :forwarded_port, guest: 80, host: 80 # SIP e SEI (Apache)
  config.vm.network :forwarded_port, guest: 9000, host: 9000 # Portainer
#   config.vm.network :forwarded_port, guest: 1521, host: 1521 # Banco de Dados (Oracle)
#   config.vm.network :forwarded_port, guest: 1433, host: 1433 # Banco de Dados (SQL Server)
#   config.vm.network :forwarded_port, guest: 3306, host: 3306 # Banco de Dados (Mysql)
#   config.vm.network :forwarded_port, guest: 8983, host: 8983 # Solr Indexer (Jetty)
#   config.vm.network :forwarded_port, guest: 8080, host: 8080 # Jod Converter
#   config.vm.network :forwarded_port, guest: 1080, host: 1080 # MailCatcher

  config.vm.provision "install-docker", type: "shell", path: "./install-docker.sh"
  config.vm.provision "install-docker-compose", type: "shell", path: "./install-docker-compose.sh"
  config.vm.provision "install-docker-machines", type: "shell", path: "./run.sh"
  config.vm.post_up_message = <<-EOF

=========================================================================
  INICIALIZAÇÃO DO AMBIENTE DE DESENVOLVIMENTO FINALIZADA COM SUCESSO ! 
=========================================================================

= Endereços de Acesso à Aplicação ========================================
Web ............................... http://localhost


= Comandos Úteis =========================================================
vagrant up                        - Inicializar ambiente do SEI
vagrant halt                      - Desligar ambiente
vagrant destroy                   - Destruir ambiente e base de testes
vagrant ssh                       - Acessar máquina virtual
vagrant status                    - Verificar situação atual do ambiente

= Debug =========================================================
PHP xDebug 3
Porta: 9003

EOF
end
