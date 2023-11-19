# Subfinder

[https://github.com/projectdiscovery/subfinder](https://github.com/projectdiscovery/subfinder)

Primero debemos configurar las APIs para que la busqueda sea mas exitosa.\
Para listar todas las apis

```
subfinder -ls
```

![label text](imgs/01.png)

Debemos configurar las API es la ruta

```
nvim /home/dxz/.config/subfinder/provider-config.yaml
```

## Buscar en un solo dominio

Para correr el programa usamos.
* Parametro -d para el dominio
* Parametro -active busca solo subdominios activos
* | lo exportamos la busqueda en un txt

```
subfinder -d hackerone.com -active | tee -a hackerone.txt
```

![label text](imgs/02.png)


## Buscar en varios dominios al mismo tiempo

* Parametro -dL ingresamos la lista de cominios a buscar los subdominios.
* Parametro -es quitar o excluir un motor de busqueda para realizar la busqueda
* Parametro -rl tiempo de espera entre cada peticion

```
subfinder -dL target.txt -active | tee -a subdomains_targets.txt
```

![label text](imgs/03.png)













