# Projecte UF3 de M04
## Entornos virtuales
[Más información.](https://docs.python.org/es/3/library/venv.html)

* ***Paso 1:*** Desde un terminal encrustado en VirtualStudio y ponermos el codigo siguiente:
    ```bash
    linux:
        python3 -m venv .venv
    ```
    ```powershell
    Amb windows:
        python -m venv .venv
    ```
* ***Paso 2:*** Ahora procedemos a activarlo:
	Amb linux:
    ```bash
		source .venv/bin/activate
    ```
	Amb Windows:
    ```powershell
		.venv\Scripts\activate
    ```
* ***Paso 3:*** Una vez tenemos creado el entorno podemos instalar los paquetes necesarios:
    ```bash
    pip install flask
	pip install feedparser

* ***Paso 4:*** Para salir del entorno usamos:
    ```bash
    desactivate
    ```
##  Modo remoto / local
**Modo Remoto:** Desde la aplicación una vez nos indican el artículo que desean ver lo buscamos en la web de la Languardia en tiempo real.

```python
def get_rss_lavanguardia(seccio):
# versió on descarrega l'XML de la web
# xml = f"https://www.lavanguardia.com/rss/{seccio}.xml"
```
**Modo Local:** Para el modo local es necesario que tengams previamente descargadas las paginas xml en una carpeta, de manera que cuando el usuario indique la página que desea ver acceda a un link local.
```python
def get_rss_lavanguardia(seccio):
    
    # versió que fa servir l'XML descarregat
    xml = f"./rss/lavanguardia/{seccio}.xml"
    
    rss = feedparser.parse(xml)
    return rss
```


    
