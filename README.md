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

# Script Convierte Dominios en IPs

Creamos el archivo le damos permisos de ejecución.
Forma de uso: ./converter.sh [domain-list-file] [output-file]

```ruby
#!/bin/bash
# Converter.sh by @xdavidhu
# This is a script inspired by the Bug Hunter's Methodology 3 by @Jhaddix
# With this script, you can convert domain lists to resolved IP lists without duplicates.
# Usage: ./converter.sh [domain-list-file] [output-file]

echo -e "[+] Converter.sh by @xdavidhu\n"
if [ -z "$1" ] || [ -z "$2" ]; then
  echo "[!] Usage: ./converter.sh [domain-list-file] [output-file]"
  exit 1
fi
echo "[+] Resolving domains to IPs..."
while read d || [[ -n $d ]]; do
  ip=$(dig +short $d|grep -oE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b"|head -1)
  if [ -n "$ip" ]; then
    echo "[+] '$d' => $ip"
    echo $ip >> $2
  else
    echo "[!] '$d' => [RESOLVE ERROR]"
  fi
done < $1
echo -e "\n[+] Removing duplicates..."
sort $2 | uniq > $2.new
mv $2.new $2
echo -e "\n[+] Done, IPs saved to '$2'."
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
