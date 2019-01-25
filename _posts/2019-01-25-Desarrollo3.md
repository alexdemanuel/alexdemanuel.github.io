---
layout: post
title:  "Desarrollo - Bucles *for* y *while*"
date:   2019-01-25 11:20:02 +0000
categories: desarrollo
---
# Bucle *for*

## 1. Escribe un script PHP que muestre los números del 1 al 10 en una tabla de una fila y 10 columnas. Utiliza un bucle *for*.

- [Documentación del bucle *for*]( http://php.net/manual/es/control-structures.for.php)

- [Creación de tablas HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)

*Resolución:*

```bash
<?php

echo "<table border='1'>";
echo "<tr>";

        for ($i = 1; $i <= 10; $i++){
            
                echo "<td> $i </td>";              
        }
        echo "</tr>"; 
echo "</table>";

?>
```

## 2. Escribe un script PHP que muestre los números del 1 al 10 en una tabla de una columna y 10 filas. Utiliza un bucle *for*.

*Resolución:*

```bash
<?php

echo "<table border='1'>";


        for ($i = 1; $i <= 10; $i++){
            echo "<tr>";
                echo "<td> $i </td>";  
            echo "</tr>";                 
        }
        
echo "</table>";
?>
```

## 3. Escribe un script PHP que muestre en una tabla los números pares que existen entre 1 y 100. Utiliza un bucle for.

*Resolución:*

```bash
<?php
// Solucion 1 
echo "<table border='1'>";
    

        for ($i = 1; $i <= 100; $i++){
            if($i % 2 == 0){
            echo "<tr>";
                echo "<td> $i </td>";
            echo "</tr>";   
            } 
        }
    
echo "</table>";

//Solucion 2
echo "<table border='1'>";
    

        for ($i = 2; $i <= 100; $i=$i+2){
            
            echo "<tr>";
                echo "<td> $i </td>";
            echo "</tr>";   
             
        }
    
echo "</table>";
?>
```


## 4. Escribe un script que muestre la tabla de multiplicar de un número aleatorio.

*Unir variables a la cadena de texto se usan los puntos. Ejemplo: echo "esto es un" .$variable. "ejemplo"*

*Resolucion:*

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

## 5. Escribe un script que muestre las tablas de multiplicar del 1 al 10.





*Resolución:*

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
## 6.Escribe un script PHP que muestre los números del 1 al 10 en una tabla en orden inverso

```bash
<?php
echo "<table border='1'>";
    echo "<tr>";

        for ($i = 10; $i >= 1; $i--){
                echo "<td> $i </td>";  
        }

    echo "</tr>";
echo "</table>";
?>
```

# Bucle *while*

## 1.1. Escribe un script PHP que muestre los números del 1 al 10 en una tabla de una fila y 10 columnas. Utiliza un bucle  while

[Documentación oficial de la función *While*](http://php.net/manual/es/control-structures.while.php)

*Resolución:*

```bash
<?php

echo "<table border='1'>";
    echo "<tr>";

        $i=1;
        while($i<=10){
            echo "<td> $i </td>";
            $i++;
        }

        echo "</tr>"; 
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

