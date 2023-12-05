# Enumeración de Subdominios

Herramientas a instalar.

## [Httpx](https://github.com/projectdiscovery/httpx)

Descargamos el binario y lo pegamos en la ruta

```ruby
unzip httpx_1.3.7_linux_amd64.zip
sudo mv httpx /usr/local/bin
```

## [Subfinder](https://github.com/projectdiscovery/subfinder)

Descargamos el binario y lo descomprimimos y lo pegamos el la ruta.

```ruby
unzip subfinder_2.6.3_linux_amd64.zip
sudo cp subfinder /usr/bin
```

Corremos la herramienta:

```ruby
subfinder -d hackerone.com | tee -a subfinder.txt
```

![label text](imgs/01.png)


## [Amass](https://github.com/owasp-amass/amass)

Descargamos el binario y lo descomprimimos y lo pegamos en la ruta.

```ruby
unzip amass_Linux_amd64.zip
mv amass_Linux_amd64/amass /usr/local/bin/
```

## [Assetfinder](https://github.com/tomnomnom/assetfinder)

Hacemos un git clone del repositorio

```ruby
git clone https://github.com/tomnomnom/assetfinder.git
cd assetfinder
go mod init assetfinder
go build .
sudo mv assetfinder /usr/local/bin
```

Para usar el programa usamos la siguiente linea de comandos

```ruby
assetfinder -subs-only hackerone.com | tee -a assetfinder.txt
```

![label text](imgs/02.png)











