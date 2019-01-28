---
layout: post
title:  "Desarrollo - Arrays con indices"
date:   2019-01-25 11:20:02 +0000
categories: desarrollo
---

# Arrays con indices

- Declarar un array 

```bash
$productos = array();
```

- Declarar, inicializar y mostrar un array

```bash
$productos = array("disco SSD","Memoria RAM", "Monitor");

echo $productos[0];
echo "</br>";
echo $productos[1];
echo "</br>";
echo $productos[2];
echo "</br>";
```
- Asignar nuevos valores al array

```bash
$productos[0] = "Este es el producto 0";
$productos[1] = "Este es el producto 1";
$productos[2] = "Este es el producto 2";

echo $productos[0];
echo "</br>";
echo $productos[1];
echo "</br>";
echo $productos[2];
echo "</br>";
```

- Consultar el contenido de un array con *print_r*

```bash
echo "<pre>";
print_r($productos);
echo "</pre>";
```

- Cómo conocer el tamaño de un array con *count*

```bash
echo "Números de elementos de array: ".count($productos);
```

- Cómo recorrer un array indexado con *for*

```bash
$numero_de_elementos = count($productos);

for ($i = 0; $i < $numero_de_elementos; $i++ ) {
    echo $productos[$i];
    echo "</br>";
}
```
## Ejercicios de arrays de indices

### 1. Escribe un script PHP que realice las siguientes acciones: 
- Inicializar un array de 10 elementos, con valores aleatorios entre 1 y 30.
- Una vez que ha inicializado el array, imprima todos los valores que almacena. 

*Resolución:*

```bash
<?php

//Declaro el array
$valores = array();


//inicializo el array con 10 numero aleatorios
for ($i=0; $i <= 9; $i++) {
    $valores[$i] = rand(1,30);
    echo "</br>";

}

// Imprimimos los valores almacenados en el array
for ($i=0; $i <10; $i++){
    echo "el Valor de $i es: ".$valores[$i];
    echo "</br>";
}
?>
```

### 2. Escribe un script PHP que realice las siguientes acciones: 
- Inicializar un array de 10 elementos, con valores aleatorios entre 1 y 30. 
- Una vez que ha inicializado el array, imprima todos los valores que almacena. 
- Calcular el valor medio de los valores del array. 
- Mostrar el valor medio que ha calculado.

*Resolución:*

```bash
<?php

//Declaro el array
$valores = array();

//inicializo el array con 10 numero aleatorios
for ($i=0; $i <= 9; $i++) {
    $valores[$i] = rand(1,30);
    echo "</br>";

}

// Imprimimos los valores almacenados en el array
for ($i=0; $i <10; $i++){
    echo "el Valor de $i es: ".$valores[$i];
    echo "</br>";

}

// Calculamos el valor medio de los valores del array
$suma = 0;
for ($i=0; $i < 10; $i++){
    $suma =$suma + $valores[$i];

}
    $media = $suma / count($valores);

    echo "El valor medio es: ".$media;
?>
```
### 3. Escribe un script PHP que realice las siguientes acciones:
- Inicializar un array de 10 elementos, con valores aleatorios entre 1 y 30.
- Una vez que ha inicializado el array, imprima todos los valores que almacena.
- Buscar el valor máximo de los valores del array.
- Muestre el valor máximo que ha encontrado.
- Muestre la posición en el array del valor máximo que ha encontrado

*Resolución:*

```bash
<?php
//Declaro el array
$valores = array();


//inicializo el array con 10 numero aleatorios
for ($i=0; $i <= 9; $i++) {
    $valores[$i] = rand(1,30);
    echo "</br>";

}

// Imprimimos los valores almacenados en el array
for ($i=0; $i <10; $i++){
    echo "el Valor de $i es: ".$valores[$i];
    echo "</br>";

}
// Averiguar cual es el valor minimo
   /* le damos un valor mas alto de los que esten en el array para que al 
    comparalo con el primer valor del array siempre se cumpla y posteriormente siga comparando
    los valores de array buscando el valor minimo
    */
$minimo = 99;
for ($i=0; $i <10; $i++){
    if( $valores[$i]<=$minimo){
        $minimo = $valores[$i];
    }
}
echo "El numero mínimo es: ".$minimo;
?>
```

### 4. Escribe un script PHP que realice las siguientes acciones:

- Inicializar un array de 10 elementos, con valores aleatorios entre 1 y 30.
- Una vez que ha inicializado el array, imprima todos los valores que almacena.
- Buscar el valor mínimo de los valores del array.
- Muestre el valor mínimo que ha encontrado.
- Muestre la posición en el array del valor máximo que ha encontrado

*Resolución;*

```bash
<?php

//Declaro el array
$valores = array();

//inicializo el array con 10 numero aleatorios
for ($i=0; $i <= 9; $i++) {
    $valores[$i] = rand(1,30);
    echo "</br>";
}

// Imprimimos los valores almacenados en el array
for ($i=0; $i <10; $i++){
    echo "el Valor de $i es: ".$valores[$i];
    echo "</br>";
}

// Averiguar cual es el valor mínimo
    /* le damos un valor mas bajo de los que esten en el array para que al 
    comparalo con el primer valor del array siempre se cumpla y posteriormente siga comparando
    los valores de array buscando el valor maximo
    */
$maximo = 0; // este valor puede ser negativo
for ($i=0; $i <10; $i++){
    if( $valores[$i] > $maximo){
        $maximo = $valores[$i];
        $posicion = $i; // para que nos indique en que posicion esta ese valor
    }
}

echo "El número máximo es: ".$maximo. "y esta en la posición: ".$posicion;
?>
```


### 5. Escribe un script PHP que sobre un array de temperaturas realice las siguientes operaciones utilizando bucles *for*:

- Calcular la media.
- Calcular el valor máximo.
- Calcular el valor mínimo.
- Mostrar todos los valores calculados.
- El array de temperaturas lo vamos a generar con números aleatorios. El array será de 10 elementos y los valores aletorios generados estarán entre 1 y 30.

*Resolución:*

```bash
<?php
//Declaro el array
$valores = array();


//inicializo el array con 10 numero aleatorios
for ($i=0; $i <= 9; $i++) {
    $valores[$i] = rand(1,30);
    echo "</br>";
}

// Imprimimos los valores almacenados en el array
for ($i=0; $i <10; $i++){
    echo "el Valor de $i es: ".$valores[$i];
    echo "</br>";
}

// Calcular valor medio
$suma = 0;
for ($i=0; $i < 10; $i++){
    $suma =$suma + $valores[$i];
}
    $media = $suma / count($valores);

    echo "El valor medio es: ".$media;
    echo "</br>";

// Averiguar cual es el valor maximo

$maximo = -1;
for ($i=0; $i <10; $i++){
    if( $valores[$i] > $maximo){
        $maximo = $valores[$i];
        $posicion = $i;
    }
}

echo "El número máximo es: ".$maximo. " y esta en la posición: ".$posicion;
echo "</br>";

// Valor Minimo
$minimo = 99;
for ($i=0; $i <10; $i++){
    if( $valores[$i]<=$minimo){
        $minimo = $valores[$i];
        $posicion = $i;
    }
}
echo "El numero mínimo es: ".$minimo. " y esta en la posición: ".$posicion;
echo "</br>";
?>
```

### 6. Escribe un script PHP que sobre un array de temperaturas realice las siguientes operaciones utilizando bucles *while*:

- Calcular la media.
- Calcular el valor máximo.
- Calcular el valor mínimo.
- Mostrar todos los valores calculados.
- El array de temperaturas lo vamos a generar con números aleatorios. El array será de 10 elementos y los valores aletorios generados estarán entre 1 y 30.

*Resolución:*

```bash
<?php
//Declaro el array
$valores = array();

//inicializo el array con 10 numero aleatorios
$i=0;
while ( $i <= 9){
    $valores[$i] = rand(1,30);
    echo "</br>";
    $i++;
}
$i=0;
 while ($i<10){
    echo "el Valor de $i es: ".$valores[$i];
    echo "</br>";
    $i++;
 }

 // Calcular valor medio
$suma = 0;
$i=0;
while($i < 10 ){
    $suma = $suma + $valores[$i];
    $i++;
}
    $media = $suma / count($valores);
    echo "El valor medio es: ".$media;
    echo "</br>";

// Valor maximo 
$maximo = -1;
$i = 0;
while ($i <10){
    if($valores[$i] > $maximo){
        $maximo = $valores[$i];
        $posicion = $i;
        }
    $i++;
}
echo "El número máximo es: ".$maximo. " y esta en la posición: ".$posicion;
echo "</br>";

// Valor minimo
$minimo = 99;
$i = 0;
while ($i <10){
    if($valores[$i] < $minimo){
        $minimo = $valores[$i];
        $posicion = $i;      
    }
    $i++;
}
echo "El número mínimo es: ".$minimo. " y esta en la posición: ".$posicion;
echo "</br>";
?>
```
### 7. Escribe un script PHP que sobre un array de temperaturas realice las siguientes operaciones utilizando bucles *do - while*:

- Calcular la media.
- Calcular el valor máximo.
- Calcular el valor mínimo.
- Mostrar todos los valores calculados.
- El array de temperaturas lo vamos a generar con números aleatorios. El array será de 10 elementos y los valores aletorios generados estarán entre 1 y 30.

*Resolución:*

```bash 
<?php
//Declaro el array
$valores = array();


//inicializo el array con 10 numero aleatorios
$i=0;
    do{
        $valores[$i] = rand(1,30);
        echo "</br>";
        $i++;
    }
while ( $i <= 9);

$i=0;
    do {
        echo "el Valor de $i es: ".$valores[$i];
        echo "</br>";
        $i++;
    }
 while ($i<10);

 // Calcular valor medio
$suma = 0;
$i=0;
    do {
        $suma = $suma + $valores[$i];
        $i++;
    }
while($i < 10 );
    $media = $suma / count($valores);
    echo "El valor medio es: ".$media;
    echo "</br>";

// Valor maximo 
$maximo = -1;
$i = 0;
    do{
        if($valores[$i] > $maximo){
            $maximo = $valores[$i];
            $posicion = $i;
            
        }
            $i++;
    }
    while ($i <10);
echo "El número máximo es: ".$maximo. " y esta en la posición: ".$posicion;
echo "</br>";

// Valor minimo
$minimo = 99;
$i = 0;
    do{
        if($valores[$i] < $minimo){
            $minimo = $valores[$i];
            $posicion = $i;
        }
            $i++;
    }
    while ($i <10);
echo "El número mínimo es: ".$minimo. " y esta en la posición: ".$posicion;
echo "</br>";
?>
```


*Documentacion Extra:*

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)

- [Documentación oficial de la estructura de control *if*](http://php.net/manual/es/control-structures.if.php)

- [Documentación oficial de la estructura de control *else*](http://php.net/manual/es/control-structures.else.php)

- [Documentación oficial del elemento de imagen *\<img>*](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img)

- [Documentación de la estructura de control switch](http://php.net/manual/es/control-structures.switch.php)

- [Documentación de la función *rand*](http://php.net/manual/es/function.rand.php)

