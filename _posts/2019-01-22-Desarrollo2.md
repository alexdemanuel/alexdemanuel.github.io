---
layout: post
title:  "Desarrollo - Estructuras de control"
date:   2019-01-21 11:20:02 +0000
categories: desarrollo
---

# 1. Escribe un script que simule el comportamiento de lanzar una moneda al aire y muestre una imagen con la cara o la cruz de la moneda.

- [Documentación oficial de la estructura de control *if*](http://php.net/manual/es/control-structures.if.php)

- [Documentación oficial de la estructura de control *else*](http://php.net/manual/es/control-structures.else.php)

- [Documentación oficial del elemento de imagen *<img>*](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img)

*Los elementos **echo** y **print** muestran cadenas de texto que se le introducen, en el caso de **echo** pueden introducirse varias pero en **print** unicamente se puede introducir una sola cadena de texto*

*Resolución*

´´´bash
// nos genera un numero entre los valores del rand y nos lo muestra 
print("Valor de rand: ");
print(rand(0,1));
echo "</br>";

//metemos el numero en una variable para luego mostrarlo
$numero = rand(0,1);
echo $numero;
echo "</br>";

//si numero es 0 entonces es cara sino, sera cruz 
if ($numero == 0) {
     echo "<img src='images/cara.jpg'>";
} else {
     echo "<img src='images/cruz.jpg'>";
}
?>
´´´

# 2. Escribe un script PHP que mediante un formulario permita introducir una nota numérica y muestre un mensaje indicando la calificación obtenida teniendo en cuenta los siguientes rangos:

*Resolución*

```bash
<?php
$nota=rand(0,10);

if ($nota >=0 && $nota <5){
    echo "Insuficiente";

} else if ($nota >=5 && $nota <6){
    echo "Suficiente";

} else if ($nota >=6 && $nota <7){
    echo "Bien";

} else if ($nota >=7 && $nota <9){
    echo "Notable";

} else if ($nota >=9 && $nota <=10){
    echo "Sobresaliente";
} 

echo "</br>";
echo $nota;

?>

```


# 3. Escribe un script PHP que mediante un formulario permita introducir una valor numérico (entre 1 y 7) y muestre un mensaje indicando a qué día de la semana corresponde. Por ejemplo, 1 sería lunes, 2 martes, etc.


- [Documentación de la estructura de control switch](http://php.net/manual/es/control-structures.switch.php)

*Resolución*
```bash
<?php

$dia=rand(1,7);
switch($dia){
    case 1:
        echo "Es Lunes";
        break;

    case 2:
        echo "Es Martes";
        break;
    
    case 3:
        echo "Es Miercoles";
        break;

    case 4:
        echo "Es Jueves";
        break;

    case 5:
        echo "Es Viernes";
        break;

    case 6:
        echo "Es Sabado";
        break;

    case 7:
        echo "Es Domingo";
}
?>
```


*Documentacion Extra:*

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)

- [Documentación de la función *rand*](http://php.net/manual/es/function.rand.php)


