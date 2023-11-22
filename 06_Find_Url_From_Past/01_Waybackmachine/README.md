# Waybackmachine

[Link Udemy](https://www.udemy.com/course/recon-for-bug-bounty-penetration-testers-ethical-hackers/learn/lecture/35462242#questions)

Pagina web que guarda el historial y cambios de muchas paginas web.

[https://web.archive.org/](https://web.archive.org/)

## Waybackurl

Waybackurls es una herramienta de línea de comandos de código abierto utilizada para extraer las URL de versiones archivadas de sitios web disponibles en el servicio de The Wayback Machine (La Máquina del Tiempo). Fue desarrollada por Tom Hudson y se utiliza mucho en el campo de la seguridad de la información y la investigación de aplicaciones web.

![https://github.com/tomnomnom/waybackurls](https://github.com/tomnomnom/waybackurls)

Instalamos con el enlace URL y movemos el binario a una ruta para poder ejecutar el comando.

```ruby
sudo mv ~/go/bin/waybackurls /usr/bin/ 
```

![label text](Imgs/01.png)

Forma de usar la herramienta, le arrojara 

```ruby
echo "hackerone.com" | waybackurls > hackerone.txt
```


















