---
layout: post
title:  "Desarrollo - Estructuras de control"
date:   2019-01-21 11:20:02 +0000
categories: desarrollo
---

#1. Escribe un script que muestre la tabla de multiplicar de un número aleatorio.

- [Documentación del bucle *for*]( http://php.net/manual/es/control-structures.for.php)

- [Creación de tablas HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)

*Unir variables a la cadena de texto se usan los puntos. Ejemplo: echo "esto es un" .$variable. "ejemplo" *

*Resolucion*

```bash
<?php
$numero=rand(1, 10);
echo "<table>";

for ($i=0; $i <=10; $i++){
    
    echo "<tr>";
        echo "<td> $numero </td>";
        echo "<td> x </td>";
        echo "<td> $i </td>";
        echo "<td> = </td>";
        echo "<td>".$numero*$i."</td>";
    echo "</tr>";

}
echo "</table>";

?>
```

# 2. Escribe un script que muestre las tablas de multiplicar del 1 al 10.





*Resolución*

```bash

<?php
$numero=rand(1, 10);
echo "<table>";
for ($numero = 1; $numero<=10; $numero++;){

    for ($i=0; $i <=10; $i++){
    
        echo "<tr>";
            echo "<td> $numero </td>";
            echo "<td> x </td>";
            echo "<td> $i </td>";
            echo "<td> = </td>";
            echo "<td>".$numero*$i."</td>"; // para unir variables a la cadena de texto se usan los .variable.
        echo "</tr>";

    }
}
echo "</table>";
?>
```


*Documentacion Extra:*

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)

- [Documentación oficial de la estructura de control *if*](http://php.net/manual/es/control-structures.if.php)

- [Documentación oficial de la estructura de control *else*](http://php.net/manual/es/control-structures.else.php)

- [Documentación oficial del elemento de imagen *\<img>*](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img)

- [Documentación de la estructura de control switch](http://php.net/manual/es/control-structures.switch.php)

- [Documentación de la función *rand*](http://php.net/manual/es/function.rand.php)

