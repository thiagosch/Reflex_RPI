# Reflex_RPI
Configuracion | Note taking


- [Configuracion del sistema](#configuracion-del-sistema)
    - [Requisitos del sistema](#requisitos-del-sistema)
    - [Configuracion del virtual enviroment](#configuracion-del-virtual-enviroment)
    - [activacion virutal enviroment](#activacion-virutal-enviroment)
    - [Instalacion de la libreria](#instalacion-de-la-libreria)
    



# Configuracion del sistema

<hr>

#### Requisitos del sistema

  ```bash
  sudo apt install python3 python3-pip libexif12 libgphoto2-6 libgphoto2-port12 libltdl7 libgphoto2-dev gphoto2
  ```
<hr>

### Configuracion del virtual enviroment
 ```bash
 mkdir ./reflex
 cd reflex
 python3 -m venv venv
 ```
### activacion virutal enviroment

```bash
source ./venv/bin/activate
```
<hr>



### Instalacion de la libreria
```bash
(venv) pip install gphoto2
```




