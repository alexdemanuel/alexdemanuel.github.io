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

//inicializo el array
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


//inicializo el array
$i=0;
    do{
        $valores[$i] = rand(1,30);
        echo "</br>";
        $i++;
    }
while ( $i < 9);

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
    while ($i <=10);
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

### 8.Escribe un script PHP que sobre un array de temperaturas realice las siguientes operaciones:

- Mostrar el listado ordenado de mayor a menor.
- Mostrar el listado ordenado de menor a mayor.

El array de temperaturas lo vamos a generar con números aleatorios. El número de elementos del array será especificado mediante un formulario y los valores aletorios generados estarán entre 1 y 30.


- [Documentación función *sort*](http://php.net/manual/es/function.sort.php)
- [Documentación función *rsort*](http://php.net/manual/es/function.rsort.php)


```bash
<?php

$numeros = array();

//inicializo el array

for ($i=0; $i <= 9; $i++) {
    $numeros[$i] = rand(1,30);
    echo "</br>";
    echo $numeros[$i];
}

$numero_de_elementos = count($numeros);
echo "<table border='1'>";
echo "<tr>";

$i=0;
for ($i=0;$i< $numero_de_elementos;$i++){
    echo "<td>$i</td>";
   echo "<br>";
}
echo "</tr>";

//ordenar numero de menor a mayor
sort($numeros);
echo "<tr>";
echo "<td> de menor a mayor";
$i=0;
for($i=0;$i< $numero_de_elementos;$i++){
    echo "<td>".$numeros[$i]."</td>";
   echo "<br>";
}
echo "</tr>";


echo "<tr>";
//ordenar numero de menor a mayor
rsort($numeros);
echo "<tr>";
echo "<td> de mayor a menor";
$i=0;
for($i=0;$i< $numero_de_elementos;$i++){
    echo "<td>".$numeros[$i]."</td>";
   echo "<br>";
}
echo "</tr>";
echo "</table>";


?>
```

## Arays asociativos

### 1. Escribe un script PHP que permita ordenar el siguiente array asociativo

- [Documentación de la función *asort*](http://php.net/manual/es/function.asort.php)
- [Documentación de la función *arsort*](http://php.net/manual/es/function.arsort.php)
- [Documentación de la función *ksort*](http://php.net/manual/es/function.ksort.php)
- [Documentación de la función *krsort*](http://php.net/manual/es/function.krsort.php)
- [Documentación de la función *foreach*](http://php.net/manual/es/control-structures.foreach.php)


*Resolución:*

```bash

<?php

$alumnos = array("Antonio"=>"31", "Maria"=>"28", "Juan"=>"29", "Pepe"=>"27");

//Orden ascencente por valor 
echo "<h2> Orden ascendente por valor (asort)</h2>";
asort($alumnos);
echo "<table border='1'>";
    foreach($alumnos as $clave => $valor){
        echo "<tr>";
        echo "<td>$clave</td>";
        echo "<td bgcolor=#FF5733>$valor</td>";
        echo "</tr>";

    }
    echo "</table>";
//Orden ascencente por Clave
echo "<h2> Orden descendente por valor (arsort)</h2>";
arsort($alumnos);
echo "<table border='1'>";
    foreach($alumnos as $clave => $valor){
        echo "<tr>";
        echo "<td>$clave</td>";
        echo "<td bgcolor=#FF5733>$valor</td>";
        echo "</tr>";

    }
    echo "</table>";
    echo "</br>";

    //Orden descencente por clave
echo "<h2> Orden ascendente por clave (ksort)</h2>";
ksort($alumnos);
echo "<table border='1'>";
    foreach($alumnos as $clave => $valor){
        echo "<tr>";
        echo "<td bgcolor=#99FF33>$clave</td>";
        echo "<td>$valor</td>";
        echo "</tr>";

    }
    echo "</table>";
    echo "</br>";

//Orden descencente por clave
echo "<h2> Orden descendente por clave (krsort)</h2>";
krsort($alumnos);
echo "<table border='1'>";
    foreach($alumnos as $clave => $valor){
        echo "<tr>";
        echo "<td bgcolor=#99FF33>$clave</td>";
        echo "<td>$valor</td>";
        echo "</tr>";

    }
    echo "</table>";

/*sacar el valor de una clave determinada del array
echo "Posicion 1: ".$alumnos["Juan"];
echo "</br>";
echo "Posicion 1: ".$alumnos['Juan'];
echo "</br>";
*/
?>
``` 

### 2.Escribe un script PHP que muestre el siguiente array asociativo ordenado por la clave. El resultado deberá seguir el siguiente patrón:

- *La capital de Italia es Roma*
- Ordenalas por clave en orden descendente (ksort)
- Los paises y capitales conviertelos en mayusculas
- Los paises en negrita
- Las capitales en cursiva 

*Resolución:*


```bash
<?php
$capitales=array("Italy"=>"Rome", "Luxembourg"=>"Luxembourg", "Belgium"=> "Brussels", "Denmark"=>"Copenhagen", "Finland"=>"Helsinki", "France" => "Paris", "Slovakia"=>"Bratislava", "Slovenia"=>"Ljubljana", "Germany" => "Berlin", "Greece" => "Athens", "Ireland"=>"Dublin", "Netherlands"=>"Amsterdam", "Portugal"=>"Lisbon", "Spain"=>"Madrid", "Sweden"=>"Stockholm", "United Kingdom"=>"London", "Cyprus"=>"Nicosia", "Lithuania"=>"Vilnius", "Czech Republic"=>"Prague", "Estonia"=>"Tallin", "Hungary"=>"Budapest", "Latvia"=>"Riga", "Malta"=>"Valetta", "Austria" => "Vienna", "Poland"=>"Warsaw");

ksort($capitales);
    foreach($capitales as $clave => $valor){
        echo "La capital de <strong>".strtoupper($clave)."</strong> es <em>".strtoupper($valor)."</em>";
        echo "</br> \n";
    }

?>
```

### 3. Escribe un script PHP que convierta el array del ejercicio anterior en un objeto JSON.

- [Documentación JSON](http://php.net/manual/es/book.json.php)
- [Documentación función *json_encode*](http://php.net/manual/es/function.json-encode.php)



*Resolución:*


```bash
<?php
$capitales=array("Italy"=>"Rome", "Luxembourg"=>"Luxembourg", "Belgium"=> "Brussels", "Denmark"=>"Copenhagen", "Finland"=>"Helsinki", "France" => "Paris", "Slovakia"=>"Bratislava", "Slovenia"=>"Ljubljana", "Germany" => "Berlin", "Greece" => "Athens", "Ireland"=>"Dublin", "Netherlands"=>"Amsterdam", "Portugal"=>"Lisbon", "Spain"=>"Madrid", "Sweden"=>"Stockholm", "United Kingdom"=>"London", "Cyprus"=>"Nicosia", "Lithuania"=>"Vilnius", "Czech Republic"=>"Prague", "Estonia"=>"Tallin", "Hungary"=>"Budapest", "Latvia"=>"Riga", "Malta"=>"Valetta", "Austria" => "Vienna", "Poland"=>"Warsaw");

echo json_encode($capitales);

?>
```

*Documentacion Extra:*

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)

- [Documentación oficial de la estructura de control *if*](http://php.net/manual/es/control-structures.if.php)

- [Documentación oficial de la estructura de control *else*](http://php.net/manual/es/control-structures.else.php)

- [Documentación oficial del elemento de imagen *\<img>*](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img)

- [Documentación de la estructura de control switch](http://php.net/manual/es/control-structures.switch.php)

- [Documentación de la función *rand*](http://php.net/manual/es/function.rand.php)

