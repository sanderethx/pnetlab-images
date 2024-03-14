# Imagem customizada do PFSENSE
<h2 aligh="center">
 Este espaço é onde insiro todo o processo de criação da imagem do PFSENSE, um firewall opensource para utilizarmos em nossos projetos.
</h2>

## 📚 Sumário

- [🚀 DOWNLOAD](#download)
- [🚀 IMPORTAÇÃO NO PNETLAB](#importação)
- [🚀 CRIAR ARQUIVO DE IMAGEM PARA O PFSENSE](#imagem)
- [🚀 CRIAR UM NÓ EM LABORATÓRIO E REALIZAR A INSTALAÇÃO DO PFSENSE](#windows)


## 🚀Criação de imagem do PFSENSE<a id="download"></a>

Você pode realizar o download do PFSENSE COMMUNITY acessando o link abaixo:
```
https://www.pfsense.org/download/
```
Escolha a arquitetura **AMD64 (64-bit)** e o Installer, selecione **DVD Image (ISO) Installer**

Clique com o botão direito do mouse sobre o botão **DOWNLOAD** e selecione a opção **COPIAR LINK**

## 🚀Importação da imagem no Pnetlab<a id="importação"></a>

Acessar o Pnetlab via SSH.
Criar uma pasta dentro das pastas de imagens QEMU do PNETLAB com o nome que deve ser iniciado com: pfsense- 
[(VEJA AQUI O PADRÃO DE CRIAÇÃO DE NOMES DE PASTAS E ARQUIVOS DE IMAGENS)](https://github.com/sanderethx/pnetlabv6/blob/main/padrao-pastas.md)

Abaixo, o exemplo de como eu criei:

```
mkdir /opt/unetlab/addos/qemu/pfsense-2.7.2-CE
```
Acessar a pasta recém criada:
```
cd /opt/unetlab/addos/qemu/pfsense-2.7.2-CE
```

Baixar a imagem dentro na pasta criada, utilizando o comando WGET + **Link copiado do botão DOWNLOAD**:

```
wget https://atxfiles.netgate.com/mirror/downloads/pfSense-CE-2.7.2-RELEASE-amd64.iso.gz
```

Descompactar o arquivo baixado:
```
gunzip pfSense-CE-2.7.2-RELEASE-amd64.iso.gz
```

Renomear o arquivo extraído para cdrom.iso:
```
mv pfSense-CE-2.7.2-RELEASE-amd64.iso cdrom.iso
```


## 🚀Criar o arquivo de imagem para o PFSENSE<a id="imagem"></a>
Neste passo, utilizaremos o **QEMU** para criar a imagem para o pfsense.
A imagem será do tipo **QCOW2** o  nome será **virtioa.qcow2**, terá o tamanho de **16GB** e poderá ser criada com esses atributos utilizando o código abaixo dentro da pasta que criamos para o PFSENSE:
[(VEJA AQUI O PADRÃO DE CRIAÇÃO DE NOMES DE PASTAS E ARQUIVOS DE IMAGENS)](https://github.com/sanderethx/pnetlabv6/blob/main/padrao-pastas.md)

```
qemu-img create -f qcow2 virtioa.qcow2 16G
```

## 🚀Ciar um nó em laboratório e realizar a instalação PFSENSE<a id="pfsense"></a>
Criaremos um nó utilizando o PFSENSE em um laboratório qualquer dentro do PNETLAB, selecionando a quantidade necessária de interfaces, CPU e memória a seu critério, onde ao iniciar o nó criado, prosseguiremos com a instalação do PFSENSE.

Acompanhe os passos seguintes através do Vídeo:
LINK AQUI.
