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

## [WaybackUrls](https://github.com/tomnomnom/waybackurls)

[Link Udemy](https://www.udemy.com/course/recon-for-bug-bounty-pentesting-ethicalhacking-by-shifa-rohit-hacktify/learn/lecture/21721090#questions)

# Escaner de URL

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






















