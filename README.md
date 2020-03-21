# docker-install
Instalação e configuração do docker no Ubuntu junto com o docker-compose

## Pré-requisitos
- Ubuntu 19.10

## Instalação do Composer

**1. Baixando a versão estavel**

```shel
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

**2. Dando permissão de execução**

```shell
$ sudo chmod +x /usr/local/bin/docker-compose
```

**3. Testando**
```shell
$ docker-compose --version
docker-compose version 1.24.1, build 4667896b
```

## Pré-instalação do Docker

**1. Atualizando pacotes**
```shell
$ sudo apt-get update
```

**2. Instalando pré-requisitos**

```shell
$ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common 
```

**3. Adicionado docker GPG key:

```shell
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

**4. Adicionando repositorio estavel**
(x86_64 / amd64)

```shell
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

## Instalando a docker engine - community

**1. Atualizando apt**

```shell
$ sudo apt-get update
```

**2. Instalando a ultima versão do Docker Engine - Community**

```shell
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```
**3. Verificando instalação**

```shell
$ sudo docker run hello-world
```

## Gerenciando o docker com usuario não root

**1. Criando grupo do docker (caso não exista)

```shell
$ sudo groupadd docker
```

**2. Adicionando seu usuario ao grupo docker**

```shell
$ sudo usermod -aG docker $USER
```
**3. Reinicie**
