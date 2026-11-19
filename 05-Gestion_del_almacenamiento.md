# Gestión del almacenamiento

## 18. Almacenamiento secundario

Guarda los datos de forma permanente.

| | HDD | SSD |
|---|---|---|
| Piezas móviles | Sí | No |
| Acceso | Depende de la posición | Rápido y uniforme |
| Coste por GB | Menor | Mayor |

En un disco duro los datos se organizan en platos, pistas y sectores. El sistema ordena las peticiones para reducir el tiempo de acceso y puede combinar discos con **RAID** para ganar rendimiento o fiabilidad.

## 19. Sistemas de archivos

Un archivo es la unidad lógica de almacenamiento. Tiene nombre, atributos (tamaño, fechas, permisos) y operaciones: crear, abrir, leer, escribir y borrar.

Los archivos se organizan en directorios jerárquicos:

```text
/
├── home
│   ├── ana
│   │   └── notas.txt
│   └── luis
├── etc
└── usr
    └── bin
```

Los permisos protegen los datos de cada usuario.

## 20. Implementación de sistemas de archivos

Un archivo se guarda en bloques del disco. Hay tres formas de asignarlos:

| Asignación | Descripción | Característica |
|---|---|---|
| Contigua | Bloques seguidos | Rápida, pero fragmenta |
| Enlazada | Cada bloque apunta al siguiente | Sin fragmentación externa |
| Indexada | Un bloque índice lista los bloques | Acceso directo |

```text
Contigua:  [ ][ ][A][A][A][ ][ ][ ]
Enlazada:  [ ][A]→[ ][ ][A]→[ ][A][ ]
Indexada:  [idx][ ][ ][A][ ][A][A][ ]
```

El sistema también controla el espacio libre (mapas de bits o listas) y usa registro de transacciones (*journaling*) para recuperarse de fallos.
