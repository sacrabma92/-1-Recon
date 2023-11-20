# GetAllUrls

[https://github.com/lc/gau](https://github.com/lc/gau)

Descargamos el repositoio y ejecutamos los siguientes comando por separado

```ruby
cd gau/cmd/gau
go build
sudo mv gau /usr/bin
gau --version;
```

Para ver las opciones de la herramienta usamos

```
gau -h
```

Para usar la herramienta la podemos usar de la siguiente forma
* Parametro entre " " el dominio a buscar rutas
* Parametro --subs busca en subdominios rutas
* Parametro --threads hilos a usar
* Parametro --o Output formato de salida

```ruby
echo "hackerone.com" | gau --subs --threads 100 --o Salida
```

Una vez termine de buscar empezamos a filtrar por parametros que nos interese buscar en las URLs

Podemos buscar por parametros\
Busca que la cadena contenga ?

```
cat Salida | grep file
cat Salida | grep -E r'\?'
```

Filtrar por archivos JS por Expresion regular

```ruby
cat Salida | grep -E *[.]js
```

























