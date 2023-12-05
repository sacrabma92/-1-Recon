# Enumeración de Subdominios

Herramientas a instalar.

## [Subfinder](https://github.com/projectdiscovery/subfinder)

Descargamos el binario y lo descomprimimos y lo pegamos el la ruta.

```ruby
sudo cp subfinder /usr/bin
```

Corremos la herramienta:

```ruby
unzip subfinder_2.6.3_linux_amd64.zip
subfinder -d hackerone.com | tee -a subfinder.txt
```

![label text](imgs/01.png)

## [Httpx](https://github.com/projectdiscovery/httpx)



























