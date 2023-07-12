# Projeto Vagrant com VirtualBox

Este projeto utiliza o Vagrant e o VirtualBox para criar uma máquina virtual com o sistema operacional Ubuntu Server 22.04.1. Ele configura a máquina virtual com os recursos necessários, como memória e CPU, e também define uma pasta compartilhada entre o host e a máquina virtual.

## Passos

Siga os passos abaixo para configurar o projeto:

### 1. Instalação do VirtualBox

Certifique-se de ter o VirtualBox instalado no seu sistema. Você pode fazer o download e a instalação a partir do site oficial do VirtualBox: [https://www.virtualbox.org](https://www.virtualbox.org)

### 2. Instalação do Vagrant

Certifique-se de ter o Vagrant instalado no seu sistema. Você pode fazer o download e a instalação a partir do site oficial do Vagrant: [https://www.vagrantup.com](https://www.vagrantup.com)

### 3. Clonar o projeto

Clone este repositório em uma pasta local do seu computador:

```shell
git clone https://github.com/seu-usuario/seu-projeto.git
cd seu-projeto
```

### 4. Configuração do Vagrant

Edite o arquivo Vagrantfile e faça as configurações necessárias. O exemplo abaixo mostra a configuração padrão utilizada neste projeto:

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "adavilag/ubuntu-server-22.04.1"
  config.vm.box_version = "1.1"
  config.vm.hostname = "ubuntu-server"
  config.vm.network "public_network", bridge: "wlp2s0"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
    vb.name = "ubuntu-server-22.04"
  end

  config.vm.synced_folder "~/Documents/Vagrant/vagrant-ubuntu", "/vagrant-ubuntu"
end
```

Certifique-se de ajustar as configurações conforme necessário, como o nome do box, a versão, a memória e as CPUs alocadas, bem como a pasta compartilhada.

### 5. Inicializar a máquina virtual

No terminal, execute o comando a seguir para inicializar a máquina virtual:

```shell
vagrant up
```

Isso irá criar a máquina virtual com base nas configurações definidas no arquivo Vagrantfile. Aguarde até que o processo seja concluído.

### 6. Acessar a máquina virtual

Após a inicialização da máquina virtual, você pode se conectar a ela via SSH. No terminal, execute o seguinte comando:

```shell
vagrant ssh
```

Agora você está conectado à máquina virtual Ubuntu Server.

### Resultado esperado

Ao concluir os passos acima, você terá uma máquina virtual Ubuntu Server 22.04.1 em execução no VirtualBox, com as configurações definidas no arquivo 'Vagrantfile'. Você poderá acessar a máquina virtual via SSH e utilizar conforme necessário.

Certifique-se de ajustar as configurações do Vagrant e do VirtualBox de acordo com suas preferências e requisitos do projeto.

Para mais informações das configurações do **Vagrantfile** acesse: [Vagrantfile personalização](Vagrantfile-personalizacao.md)