---
layout: post
title:  "Desarrollo - Funciones"
date:   2019-01-25 11:20:02 +0000
categories: desarrollo
---
# Funciones

## Introducción de funciones

- [Documentación funciones definidas en PHP](http://php.net/manual/es/functions.user-defined.php)
- [Devolver valores de una función PHP](http://php.net/manual/es/functions.returning-values.php)

```bash
<?php

//Definicion de funcion
function mi_primera_funcion(){
    echo "Esto es una funcion";
}

//Invocacion/LLamada de una funcion

mi_primera_funcion();
echo "</br>";

function suma($numero1, $numero2){
    return $numero1 + $numero2;

}
//forma 1 de mostrar resultado
$resultado = suma(3,100);
echo "Suma: $resultado";
echo "</br>";

//forma 2 de mostrar el resultado
echo "Suma: ".suma(3,100);
// cada funcion unicamente devuleve 1 solo valor en caso de querer 2 valores hay que hacer 2 funciones

function producto($numero1, $numero2){
    return $numero1 * $numero2;

}
echo "producto: ".producto(3,100);
?>
```
## Ejercicios de funciones

### 1. Escribe una función que reciba dos parámetros de entrada (inicio y fin) y que imprima las tablas de multiplicar entre esos dos números. Utilice la función del ejercicio anterior.

```bash
<?php
//funcion para sacar la tabla de multiplicar de un numero 
function multiplicar($numero){
    echo "<h2> Tabla de multiplicar de $numero </h2>";
    echo "<table border=1 cellpadding=5>";
    
    
    for($i=0; $i<=10; $i++){
      
        echo "<tr>";
        echo "<td>$numero</td>";
        echo "<td> X </td>";
        echo "<td> $i </td>";
        echo "<td> = </td>";
        echo "<td>".($numero * $i)."</td>"; 
        echo "</tr>";
    }
    
    echo "</table>";
}

//imprimimos todas las tablas del 1-10
function imprimir_tablas($inicio, $fin){
    for($i=$inicio; $i<=$fin; $i++){
        multiplicar($i);
    }
}
imprimir_tablas(1,10);

?>
```

### 3. Escribe una función llamada inicializar_array que reciba tres parémetros llamados numero_de_elementos, min y max, y que devuelva un array de números enteros comprendidos entre los valores min y max. El número de elementos que contiene el array será el especificado en el parámetro de entrada numero_de_elementos

```bash 
<?php

//inicializa un array de un numero determinado de elementos randoms que se situan entre un valor minimo y maximo fijado
function inicializar_array($numero_elementos, $min, $max){
    $numeros = array();
    for ($i=0; $i < $numero_elementos; $i++){
        $numeros[$i] = rand($min, $max); // mete un numero aleatorio entre el max y en min en la casilla que inidque $i en el array
    }

    return $numeros;
}

$lista = inicializar_array(10, 1, 40);

?>
```

### 3. Crea un archivo llamado funciones.php que reciba un array como parámetro de entrada y que devuelva los siguientes valores
    - Valor medio
    - Valor máximo
    - Valor mínimo

- Funciones.php

```bash
<?php

// Array de valores a introducir 


function inicializar_array($numero_elementos, $min, $max){
    $numeros = array();
    for ($i=0; $i < $numero_elementos; $i++){
        $numeros[$i] = rand($min, $max);
    }

    return $numeros;
}

//Calcular media 

function calcular_media($lista){
    $suma=0;
    $numero_elementos = count($lista);
        for ($i = 1;$i< $numero_elementos; $i++){
            $suma = $suma + $lista[$i];
        }
    $media = $suma / $numero_elementos;
    return $media;
}




// Calcular maximo

function calcular_max($lista){
    $maximo = -1;
    $numero_elementos = count($lista);
        for ($i = 1; $i < $numero_elementos; $i++){    
            if ($lista[$i] > $maximo){
                $maximo = $lista[$i];
            }
        }   
    
    return $maximo;

}


// Calcular minimo

function calcular_min($lista){
    $minimo = 99;
    $numero_elementos = count($lista);
        for ($i = 1; $i < $numero_elementos; $i++){    
            if ($lista[$i] < $minimo){
                $minimo = $lista[$i];
            }
        }   
    
    return $minimo;

}
?>
```

- Index.php

```bash
<?php

include ('funciones.php');

echo dirname(__FILE__); // nos muestra la ruta del arvhivo en el que nos encontramos
echo "</br>";

$lista = inicializar_array(10 ,1 ,30);
$media = calcular_media($lista);
$max = calcular_max($lista);
$min = calcular_min($lista);

echo "La media es: ".$media;
echo "</br>";
echo "El maximo es:".$max;
echo "</br>";
echo "El minimo es: ".$min;

?>
```

*Documentacion Extra:*

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)

- [Documentación oficial de la estructura de control *if*](http://php.net/manual/es/control-structures.if.php)

- [Documentación oficial de la estructura de control *else*](http://php.net/manual/es/control-structures.else.php)

- [Documentación oficial del elemento de imagen *\<img>*](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img)

- [Documentación de la estructura de control switch](http://php.net/manual/es/control-structures.switch.php)

- [Documentación de la función *rand*](http://php.net/manual/es/function.rand.php)
