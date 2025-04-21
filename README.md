# Script de Provisionamento de Servidor Web (Apache)

Este repositório contém um script Bash simples para provisionamento de um servidor web com Apache em distribuições baseadas em Debian/Ubuntu.

## O que o script faz:

1. Atualiza o sistema operacional.
2. Instala o Apache2 e o unzip.
3. Baixa uma página web de teste hospedada no GitHub.
4. Descompacta o arquivo baixado.
5. Copia os arquivos da página para o diretório padrão do Apache (`/var/www/html/`).

## Script

```bash
#!/bin/bash

echo "Script de Provisionamento de um Servidor Web (Apache)"

echo "Atualizando sistema operacional"
apt-get update -y
apt-get upgrade -y

echo "Instalando o serviço Apache"
apt-get install apache2 -y
apt-get install unzip -y

echo "Baixando pagina de teste"
cd /tmp
wget https://github.com/denilsonbonatti/linux-site-dio/archive/refs/heads/main.zip
unzip main.zio
cd linux-site-dio

echo "Enviando arquivos para pasta padrão do apache"
cp -R * /var/www/html/

echo "Script finalizado"
