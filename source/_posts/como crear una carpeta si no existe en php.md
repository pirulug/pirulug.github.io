---
extends: _layouts.post
section: content
title: Cómo crear una carpeta si no existe en PHP
date: 2022-05-08
author: Pirulug
description: Es una descripcion.
featured: false
categories: [php]
---

1. `file_exists()`  para comprobar si un archivo o directorio existe en PHP
2. `is_dir()`  para comprobar si un archivo o directorio existe en PHP
3. `file_exists()`  vs  `s_dir()`  en PHP
4. `mkdir()`  en PHP

Es posible crear una carpeta y establecer el permiso apropiado usando PHP, específicamente usando la función  `mkdir()`.

El modo de permiso por defecto es  `0777`  (el acceso más amplio posible). Antes de crear un directorio, es importante comprobar primero si el directorio o un archivo existe o no. En PHP, puede hacerse usando  [`file_exists`](https://www.php.net/manual/en/function.mkdir.php)  o  [`is_dir`](https://www.php.net/manual/en/function.is-dir.php).

**`file_exists()`  para comprobar si un archivo o directorio existe en PHP**

La función  `file_exists`  es una función incorporada para comprobar dónde existe o no un directorio o un archivo. Acepta un parámetro de un camino que devuelve  `true`  si ya existe o  `false`  si no.

Ejemplo usando  `file_exists()`:

```php
$path = "sample/path/newfolder";
if (!file_exists($path)) {
    mkdir($path, 0777, true);
}
```

En el ejemplo anterior, comprueba la existencia del directorio usando la función  `file_exists()`, luego crea el directorio  `newfolder`  si el resultado es falso, con el permiso de  `0777`.

**`is_dir()`  para comprobar si un archivo o directorio existe en PHP**

Esta función también es similar a  `file_exists`, y la única diferencia es que sólo devolverá  `true`  si la cadena pasada es un directorio y devolverá  `false`  si es un archivo.

Ejemplo usando  `is_dir`:

```php
$path = "sample/path/newfolder";
if (!is_dir($path)) {
    mkdir($path, 0777, true);
}
```

En el ejemplo anterior,  `is_dir`  comprueba si la carpeta ya existe antes de crear una nueva carpeta usando  `mkdir`.

**`file_exists()`  vs  `s_dir()`  en PHP**

Ambas funciones comprueban la existencia del directorio, la única diferencia es que  `file_exists()`  también devuelve  `true`  si el parámetro pasado es un archivo. Por otro lado,  `is_dir`  es un poco más rápido que  `file_exists`.

**`mkdir()`  en PHP**

Esta función crea un directorio que se especifica por ruta que se pasa como parámetro. El valor de retorno esperado es  `true`  o  `false`.

Ejemplo de implementación:

```php
mkdir($path, $mode, $recursive, $context);
```

**Valores de los parámetros**

Parámetro

Valores

`path`  (requerido)

Directorio o ruta para crear

`mode`  (opcional)

Permiso de directorio o de archivo. Por defecto, el  `mode`  es  `0777`  (acceso más amplio posible).  
El  `mode`  está compuesto por cuatro números:  
**1st**  - Siempre establecido en  `0`  
**2nd**  - Especifica el permiso del propietario del directorio o archivo.  
**3rd**  - Especifica el permiso del grupo de usuarios del propietario  
**4th**  - Especifica el permiso de todos los demás.

`recursivo`  (opcional)

(`true`  o  `false`)  
Para crear la estructura anidada, el parámetro  `recrusive`  debe establecerse en  `true`.

`context`  (opcional)

Conjunto de parámetros que mejoran o modifican el comportamiento de la corriente.

**Nota:**  PHP comprueba si el script operativo en el directorio tiene el mismo UID(propietario) en el directorio cuando el  `safe mode`  está activado.
