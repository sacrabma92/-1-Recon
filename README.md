# Convert Icon Base64 for Shodan

```ruby
# python 3

import mmh3
import requests
import codecs
 
response = requests.get('https://cybersecurity.wtf/favicon.ico')
favicon = codecs.encode(response.content,"base64")
hash = mmh3.hash(favicon)
print(hash)
```

# Httpx
Descargamos el binario le damos permisos de ejecución y lo copiamos en la ruta /usr/bin

[https://github.com/projectdiscovery/httpx](https://github.com/projectdiscovery/httpx)

# Assetfinder
[https://github.com/tomnomnom/assetfinder](https://github.com/tomnomnom/assetfinder)

```ruby
sudo apt install assetfinder -y
```

# Anew
Descargamos el binario damos permisos de ejecución y lo copiamos a la ruta /usr/bin

[https://github.com/tomnomnom/anew](https://github.com/tomnomnom/anew)

# Httprobe
Descargamos el binario damos permisos de ejecución y lo copiamos a la ruta /usr/bin
Para descromprimir

[https://github.com/tomnomnom/httprobe](https://github.com/tomnomnom/httprobe)

```ruby
tar xvf .....
```
# Findomain

[https://github.com/Findomain/Findomain](https://github.com/Findomain/Findomain)

# fff
Descargar el repositorio, e ingresamos en la carpeta y ejecutamos

[https://github.com/tomnomnom/fff](https://github.com/tomnomnom/fff)

Compilamos el programa y lo copiamos en /usr/bin

```
go build
```
