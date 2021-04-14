# my-listen

Se trata de crear un script que liste los puertos que se encuentran
escuchando en la maquina que lo corre.

Debe recibir como parametro el protocolo (tcp o udp) e imprimirlos
sin repetir y ordenados de menor a mayor.

Por ejemplo:
Para puertos tcp:

```sh
./my-listen --tcp
List open TCP ports on local machine:
*   80
*   22
*   443
```

## Implementacion

El script es [my-listen](./my-listen).

El mismo debe recibir uno de los protocolos como parametro:

| short | long |
| --- | --- |
| -t | --tcp |
| -u | --udp |

Internamente utiliza el comando ss con las opciones:

| opcion | descripcion |
| --- | --- |
| -n  | Muestra los puertos en forma numerica |
| -l  | Muestra los sockets que se encuentran escuchando unicamente |
| -H  | No muestra el header |
| -u o -t | tcp o udp segun se reciba como parametro |

Luego realiza una serie de pipes donde:

* se seleccionan solo el numero de puerto (junto con :)
* se ordenan
* se eliminan los duplicados
* se reemplazan los ":" por un "\*\t"

