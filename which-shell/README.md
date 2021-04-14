# which-shell

Este script muestra para cada usuario su shell configurado.

Adicionalmente recibe como parametro una cadena de filtrado.

Ejemplo:
```sh
./which-shell
root:/bin/bash
daemon:/usr/sbin/nologin
...
sys:/usr/sbin/nologin
sync:/bin/sync
...
```

```sh
./which-shell sy
sys:/usr/sbin/nologin
sync:/bin/sync
```

## Implementacion

El script es [which-shell](./which-shell).

Internamente lista el archivo /etc/passwd y lo separa en columnas
utilizando ":" como delimitador, para quedarse con la primer y 
septima columna (las correspondientes al usuario y el shell asignado).

Por ultimo, si recibe un argumento lo utiliza para filtrar los resultados
con grep.


