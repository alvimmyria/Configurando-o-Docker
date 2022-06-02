#DOCKER E KUBERNETES#

- sudo amazon-linux-extras install docker
- sudo service docker start
- sudo usermod -a -G docker ec2-user
- sudo chkconfig docker on 
- docker --version
- docker run helloworld

CRIAR PASTA
- mkdir site

ENTRAR NA PASTA 
- cd site\ (entrar na pasta)
- TWORPTESTE="true100%"

CRIAR A VARIAVEL 
- export VAR="true100%" 

MUDAR O FUSO HORÁRIO
- export TZ="US/Pacific" 

VER DATA E FUSO
- date  

VER VARIAVEL 
- echo TWORPTEST="true100%" 

INICIANDO UM CONTAINER
- docker run --name Container1 -it ubuntu bash

CONTAINER RODAR
sudo docker ps -a 

PARAR CONTAINER
- sudo docker stop Container1

FINALIZAR 
- sudo docker kill Container1

DEPLOY KUBERNETES
- Instalar p minikube
- minikube start

VISUALIZAR IP
- minikube ip

VER CLUSTER INSTALADO
- kubectl config use-context minikube

APLICAÇÃO 
- loop do
- puts 'Helloworld!'
- STDOUT.flush
- sleep 1
- end

CRIANDO DOCKERFILE
- FROM ruby:2.6-alpine
- COPY . /app
- WORKDIR /app

NO TERMINAL
- ["ruby", "app.rb"]

CRIAR DOCKER HUB IMAGE
- docker build . -t <myria>/dummy-logger:1.0
- docher push <myria>/dummy-logger:1.0

ARQUIVO KUBERNETES
- apiVersion: v1
- kind: Pod
- metadata:
- name: dummy-logger
- spec:
- containers:
- name: logger-container
- image: <sarahalvim>/dummy-logger:1.0

ALOCAR A CONFIGURAÇÃO KUBERNETES 
- kubectl create -f pod-1.Container1

LOGS DA APLICAÇÃO
- kubectl logs --follow dummy-logger

CRIANDO UM DEPLOYMENT 
- kubectl create deployment Container1 --image=k8s.gcr.io/echoserver:1.4

VER DEPLOYMENT
- kubectl get deployments

CRIANDO UM SERVIÇO
- kubectl expose deployment MeuContainer --type=LoadBalancer --port=443 (exemplo de uma porta)

VER SERVIÇOS
- kubectl get services

CRIANDO UM SECRET 
- Armazenar o usuário em um arquivo ./username.txt e a senha em um arquivo ./password.txt na sua máquina local.
- echo -n 'admin' > ./.txt
- echo -n '1f2d1e2e67df' > ./password.txt

EMPACONTANDO SERVIÇOS DE UMA SECRET 
- kubectl create secret generic db-user-pass \
- --from-file=./MinhaSecret.txt \
- --from-file=./123456.txt

VERIFICANDO UMA SECRET
- kubectl get secrets


#CONFIGURANDO E INICIALIZANDO O VAGRANT#

INSTALAR O VAGRANT E O VIRTUALBOX
- apt -get install virtualbox
- sudo apt -get install virtualbox
- sudo apt -get install vagrant


NO TERMINAL
vagrand --version 
(ver se a versão está correta)

CRIAR MÁQUINA VIRTUAL
Acessar pasta 
- mkdir nomedapasta
- cd nomedapasta
- /nomedapasta

CRIAR ARQUIVO INDEX HTML
- index.html
<h1>Hello World</h1>

PROCESSO DE CRIAÇÃO DA MÁQUINA
- vagrant init
- mkdir -p /root/projetos/CentOs7
- cd ~/projetos/CentOs7

CRIAR ARQUIVO COM ESPECIFIÇÕES DO AMBIENTE
- vim vagrantfile

INICIAR AMBIENTE DE DESENVOLVIMENTO
- vagrant up

ACESSAR O AMBIENTE VIA TERMINAL
- vagrant ssh 

DENTRO DA MÁQUINA VIRTUAL
- cd /vagrant
- ls
- vim index.html

INICIAR SERVIDOR EM RUBY
- ruby -run -e httpd . -p 3100 (ex de número de uma porta)
(não será possível acessar o localhost)

- vim vagrantfile
(configurar o redirecionamento da porta 3100 para acesso ao localhost)
- wq
(salvar)
- vagrand reload
(reiniciar)
- vagrant ssh
- cd /Vagrant
- ruby -e httpd . -p 3100
(será possível acessar o HelloWorld via localhost)

CONFIGURANDO O CentOS 
- mkdir -/class_vms
- sudo vagrant init /centos7
- sudo vagrant up
- sudo vagrant ssh

USUARIOS DA MAQUINA VIRTUAL 
usermod -a -G vboxusers guilherme
usermod -a -G vboxusers rene
usermod -a -G vboxusers cristiano
usermod -a -G vboxusers kevin
usermod -a -G vboxusers mario
usermod -a -G vboxusers lucas
usermod -a -G vboxusers ioram
usermod -a -G vboxusers matheus

COMPARTILHANDO AS PORTAS

ALTERANDO VANGRANTFILE 
- Vagrant.configure(2) do |config|
- config.vm.box = "centos7"
- config.vm.provision :shell, path: "nginx.sh"
- config.vm.network :forwarded_port, guest: 80, host: 8888
- end

TESTANDO O AMBIENTE
TESTAR AMBIENTE
Criar arquivo index :
<html>
<head><title>TESTE</title></head>
<body>
<h1>FUNCIONA!</h1>
</body>
</html>

CONECTAR A MÁQUINA VIRTUAL
- vagrant rdp



------------------------------------------------
CRIANDO UM PROGRAMA PYTHON

NO TERMINAL

INSTALAÇÃO PYTHON
- pip install pyinstaller

- print (helloworld)

NO TERMINAL OU PROMPT DE COMANDO
- python nomedoarquivo.py

OBTER A MENSAGEM 
- helloworld

VER VERSÃO 
- pyinstaller --version

PYTHON EM JAVA

INSTALAÇÃO 
- java jython

ACESSAR DIRETÓRIO
- jython

INSTALANDO O APACHE ZEPPELIN
- sudo tar xf zeppelin-*-bin-all.tgz -C /opt

RENOMEAR O DIRETÓRIO
- sudo mv /opt/zeppelin-*-bin-all /opt/zeppelin

CRIANDO O SYSTEMD
- sudo nano /etc/systemd/system/zeppelin.service

INICIALIZAÇÃO 
- sudo systemctl enable zeppelin

INICIAR ZEPPELIN
- sudo systemctl start zeppelin
































