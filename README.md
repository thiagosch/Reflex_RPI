# Reflex_RPI
Configuracion | Note taking


- [Configuracion del sistema](#configuracion-del-sistema)
    - [Requisitos del sistema](#requisitos-del-sistema)
    - [Configuracion del virtual enviroment](#configuracion-del-virtual-enviroment)
    - [activacion virutal enviroment](#activacion-virutal-enviroment)
    - [Instalacion de la libreria](#instalacion-de-la-libreria)
- [Configuracion](#configuracion)
    - (Incrementar SWAP)[#incrementar-swap] 

<hr>

# Configuracion del sistema


#### Requisitos del sistema

  ```bash
  sudo apt install python3 python3-pip libexif12 libgphoto2-6 libgphoto2-port12 libltdl7 libgphoto2-dev gphoto2
  ```


### Configuracion del virtual enviroment
 ```bash
 mkdir ./reflex
 cd reflex
 python3 -m venv venv
 ```
#### activacion virutal enviroment

```bash
source ./venv/bin/activate
```

#### Instalacion de la libreria
```bash
(venv) pip install gphoto2
```

<hr>

# configuracion
### Incrementar SWAP
<details>

<summary>Por que?</summary>
SWAP = Ram en disco
Cuando la ram se llena linux automaticamente comienza a utilizar el disco como RAM, una vez la RAM y SWAP se llenan el sistema va a entrar en un estado de bloqueo, si el consumo no disminuye, el sistema quedara bloqueado completamente

Al trabajar con solo 512MB de ram, cualquier proceso relativamente pesado va a empezar a consumir SWAP, configurado en 200MB por defecto, con esta modificacion sube a 2GB.

Esta modificacion nos asegura que el sistema no se bloquee.

</details>


Editar el archivo `/etc/dphys-swapfile`
```bash
sudo nano /etc/dphys-swapfile
```

modificar la linea `CONF_SWAPSIZE=200`(200MB) cambiar por `CONF_SWAPSIZE=2000` (2GB)

Reiniciar el servicio de SWAP
```bash
sudo /etc/init.d/dphys-swapfile restart
```



