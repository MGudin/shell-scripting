# ip-collect

Script que muestra las direcciones ip de la PC indicando mascara de
subred separadas por coma.

Ejemplo:
```sh
./ip-collect
127.0.0.1/8,192.168.30.176/24,172.17.0.1/16
```

## Implementacion

El script es [ip-collect](./ip-collect). No recibe parametros.

Utiliza el comando ip para mostrar las interfaces junto con sus direcciones
ip asignadas. 

Mediante pipes se seleccionan las direcciones ip, para luego unirlas con comas.

Finalmente se elimina la ultima coma.
