# Reflex_RPI
Configuracion | Note taking


[Documentacion gphoto2](http://www.gphoto.org/doc/manual/ref-gphoto2-cli.html)

- [Configuracion del sistema](#configuracion-del-sistema)
    - [Requisitos del sistema](#requisitos-del-sistema)
    - [Configuracion del virtual enviroment](#configuracion-del-virtual-enviroment)
    - [activacion virutal enviroment](#activacion-virutal-enviroment)
- [Configuracion](#configuracion)
    - (Incrementar SWAP)[#incrementar-swap] 

<hr>

# Configuracion del sistema


#### Requisitos del sistema

  ```bash
  sudo apt install python3 python3-pip gphoto2
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

<hr>

# configuracion
### Incrementar SWAP
<details>

<summary>Por que?</summary>

> SWAP = parte del disco(tarjeta SD) que se utiliza como RAM
> 
> Cuando la ram se llena linux automaticamente comienza a utilizar el disco como RAM, una vez la RAM y SWAP se llenan el sistema va a entrar en un estado de bloqueo, si el consumo no disminuye, el sistema quedara bloqueado indefinidamente
> 
> Al trabajar con solo 512MB de ram, cualquier proceso relativamente pesado va a empezar a consumir SWAP, configurado en 200MB por defecto, con esta modificacion subimos el espacio de SWAP a 2GB.
> 
> Posiblemente sea necesario solo para desarrollo(ya que uso vscode remote ssh para desarrollar y esto consume mucha RAM del sistema), pero teniendo en cuenta la inestabilidad que podria traer quedarse sin SWAP, recomiendo hacerlo en los equipos de produccion.

</details>


Editar el archivo `/etc/dphys-swapfile`, modificar la linea `CONF_SWAPSIZE=200`(200MB) cambiar por `CONF_SWAPSIZE=2000` (2GB)
```bash
sudo nano /etc/dphys-swapfile
```



Reiniciar el servicio de SWAP
```bash
sudo /etc/init.d/dphys-swapfile restart
```



