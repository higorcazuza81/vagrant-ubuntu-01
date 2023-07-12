# Documentação do Vagrantfile

O Vagrantfile é o arquivo de configuração usado pelo Vagrant para criar e provisionar máquinas virtuais. Neste projeto, o Vagrantfile foi criado com o objetivo de configurar uma máquina virtual Ubuntu Server 22.04.1 para facilitar o desenvolvimento de aplicativos baseados em Ubuntu. Nesta documentação, vamos explicar as configurações e opções disponíveis no Vagrantfile, bem como como personalizá-lo para atender às suas necessidades.

## Configurações

### Configuração da caixa (box)
```ruby
config.vm.box = "adavilag/ubuntu-server-22.04.1"
config.vm.box_version = "1.1"
```

Essas configurações definem a caixa (box) a ser utilizada para criar a máquina virtual. A caixa "adavilag/ubuntu-server-22.04.1" é uma imagem pré-configurada do Ubuntu Server 22.04.1. A opção box_version especifica a versão específica da caixa a ser usada. Você pode alterar essas configurações para usar uma caixa diferente, conforme necessário.

### Configuração do hostname
```ruby
config.vm.hostname = "ubuntu-server"
```
Essa configuração define o nome do hostname da máquina virtual. Neste caso, o hostname será definido como "ubuntu-server". Você pode alterar o valor para definir um hostname diferente para a máquina virtual.

### Configuração da rede
```ruby
config.vm.network "public_network", bridge: "wlp2s0"
```

Essa configuração define a rede da máquina virtual. No exemplo acima, uma interface de rede pública é configurada usando a opção "public_network". A opção bridge especifica a ponte de rede a ser usada. Certifique-se de ajustar a opção bridge para corresponder à interface de rede correta do seu sistema.

### Configuração do hardware
```ruby
config.vm.provider "virtualbox" do |vb|
  vb.memory = "1024"
  vb.cpus = 1
  vb.name = "ubuntu-server-22.04"
end
```

Essa configuração define o hardware da máquina virtual. No exemplo acima, a máquina virtual terá 1024 MB de memória (**vb.memory**) e 1 CPU (**vb.cpus**). O valor dessas configurações pode ser ajustado conforme necessário para atender aos requisitos do seu projeto. A opção **vb.name** especifica o nome da máquina virtual.

### Configuração de pasta compartilhada
```ruby
config.vm.synced_folder "~/Documents/Vagrant/vagrant-ubuntu", "/vagrant-ubuntu"
```

Essa configuração define uma pasta compartilhada entre o sistema host e a máquina virtual. No exemplo acima, a pasta "~/Documents/Vagrant/vagrant-ubuntu" do sistema host é sincronizada com o caminho "/vagrant-ubuntu" na máquina virtual. Você pode ajustar o caminho da pasta compartilhada para corresponder ao local correto no seu sistema host.

### Personalização

O Vagrantfile pode ser personalizado de várias maneiras para atender às suas necessidades específicas. Aqui estão algumas opções comuns de personalização:

Personalizar as configurações da caixa (box): Você pode escolher uma caixa diferente, como uma versão mais recente do Ubuntu Server, ou até mesmo uma distribuição Linux diferente, conforme necessário. Consulte o diretório de caixas do Vagrant (Vagrant Box Catalog) para encontrar outras opções disponíveis.

Ajustar as configurações de hardware: Dependendo dos requisitos do seu projeto, você pode aumentar ou diminuir a quantidade de memória (**vb.memory**) e o número de CPUs (**vb.cpus**) alocados para a máquina virtual.

Configurar redes adicionais: Além da rede pública, o Vagrant suporta várias opções de rede, como redes privadas e redes internas. Consulte a documentação do Vagrant para obter mais informações sobre como configurar redes adicionais.

Adicionar provisionamento: O Vagrant permite adicionar scripts de provisionamento para configurar automaticamente a máquina virtual. Você pode adicionar scripts para instalar pacotes, configurar servidores, criar usuários, entre outros.

Configurar plugins: O Vagrant tem uma grande variedade de plugins disponíveis que podem estender suas funcionalidades. Você pode explorar os plugins disponíveis e adicionar aqueles que são relevantes para o seu projeto.

Lembre-se de executar o comando **vagrant reload** após fazer alterações no Vagrantfile para aplicar as alterações na máquina virtual.

### Conclusão

O Vagrantfile é a chave para criar e configurar máquinas virtuais de forma fácil e repetível. Nesta documentação, explicamos as configurações disponíveis no Vagrantfile e como personalizá-lo para atender às suas necessidades específicas. Com o Vagrant, você pode criar ambientes de desenvolvimento consistentes e reproduzíveis para seus projetos baseados em Ubuntu.



