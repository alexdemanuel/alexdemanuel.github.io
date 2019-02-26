---
layout: post
title:  "Desarrollo - Formularios con PHP"
date:   2019-01-25 11:20:02 +0000
categories: desarrollo
---
#Formularios con PHP

[Documentación de la variable superglobal *$_GET*](http://php.net/manual/es/reserved.variables.get.php)
[Documentación de la función empty](http://php.net/manual/es/function.empty.php)
[Formularios HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms)

## 1. Escribe un script que muestre un formulario con un campo de texto y que permita enviarlo usando el método GET. El mismo script será capaz de recibir el dato enviado por el formulario y lo mostrará.

*Formulario:*
```bash
<!DOCTYPE html>
<html>
<head>
</head>
<body>

<?php

if(empty($_GET["user_name"]) != 1){
    echo "<h2> Bienvenido a IAW: ".$_GET["user_name"]."</h2>";
}
?>

<form action="index.php" method="GET">
    <div>
        <label for="name">NAME:</label>
        <input type="text" id="name" name="user_name">
        <button type="submit">Enviar</button>
    </div>
</form>
</body>
</html>

```

## 2. Escribe un script que muestre un formulario con un campo de texto y que permita enviarlo usando el método POST. El mismo script será capaz de recibir el dato enviado por el formulario y lo mostrará.

```bash
<!DOCTYPE html>
<html>
<head>
</head>
<body>

<?php

if(empty($_POST["user_name"]) != 1){
    echo "<h2> Bienvenido a IAW: ".$_POST["user_name"]."</h2>";
}
?>

<form action="index.php" method="POST">
    <div>
        <label for="name">NAME:</label>
        <input type="text" id="name" name="user_name">
        <button type="submit">Enviar</button>
    </div>
</form>
</body>
</html>

```
## 3. Escribe un script que muestre un formulario que permita introducir un número y mostrar su tabla de multiplicar.

- *Index.php*
```bash
<!DOCTYPE html>
<html>
<head></head>
<body>

<form action="index.php" method="POST">
    <div>
        <label for="tabla">Tabla de multiplicar:</label>
        <input type="number" id="tabla" name="tabla">
        <button type="submit">Enviar</button>
    </div>


<?php
include("funciones.php");
 $numero = $_POST["tabla"];

if( !empty($numero) ){
    multiplicar($numero);
}

?>
</form>  
</body>
</html>

```

- *Funciones.php*

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
        echo "<td>".($numero * $i)."</td>";  //tambien funciona la cuenta sin el parentesis 
        echo "</tr>";
    }
    
    echo "</table>";
}
?>

```

## 4. Escribe un script que mediante un formulario permita seleccionar el número de monedas que se desean lanzar (de 1 a 20) y el tipo de moneda (Dólar Estadounidense, Euro, Yen japonés, Libra esterlina, Franco suizo). El comportamiento tiene que ser similar al de la web random.org.

*Las imagenes de las monedas las encontraran tanto en la web wandom.org como en el repositorio que se encuentra en la parte baja de la página*

```bash
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Page Title</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">

</head>
<body>

<h2>4. Escribe un script que mediante un formulario permita seleccionar el número de monedas que se desean lanzar (de 1 a 20) y el tipo de moneda (Dólar Estadounidense, Euro, Yen japonés, Libra esterlina, Franco suizo). El comportamiento tiene que ser similar al de la web random.org.

</h2>

<form action="index.php" method="POST">
    <div>
        <label for="number_of_coins">numero de monedas:</label>
        <input type="number"id="number_of_coins" name="number_of_coins">

        <label for="monedas">Tipo de moneda:</label>
        <select name="type_of_coins">
            <option selected value="1" >Selecciona el tipo de moneda</option>
            <option value="2">Dólar Estadounidense</option>
            <option value="3">Euro</option>
            <option value="4">Yuan Chino</option>
            <option value="5">Franco Suizo</option>
            <option value="6">Peso Colombiano</option>
        </select>

      <!--  <label for="range">Rango:</label>
        <input type="range" min="0" max="1" id="range" name="rango">


        -->
            <button type="submit">Enviar</button> 
            
    </div>

<?php
$number_of_coins = $_POST["number_of_coins"];
$type_of_coins = $_POST["type_of_coins"];
$range = $_POST["range"];

//print_r($_POST);

if(empty($number_of_coins) || $type_of_coins == 1){
    echo "<h2>Has de introducir los datos en todos los campos</h2>";

}else{
/*if( !empty($number_of_coins) && empty($type_of_coins)!= 1 ){
    echo "<h2>$number_of_coins</h2>";

    echo "<h2>$type_of_coins</h2>";
  */

    for($i=1; $i <= $number_of_coins; $i++){
        $numero = rand(0,1);

        //Dolares
        if ($type_of_coins == 2 && $numero == 0){
            echo "<img src='images/dolar-obverse.jpg'</img>";
        }else if($type_of_coins == 2 && $numero == 1 ){
            echo "<img src='images/dolar-reverse.jpg'</img>";
        }

        //Euros
        if ($type_of_coins == 3 && $numero == 0){
            echo "<img src='images/euro-obverse.jpg'</img>";
        }else if($type_of_coins == 3 && $numero == 1 ){
            echo "<img src='images/euro-reverse.jpg'</img>";
        }

        //Chinese YUAN
        if($type_of_coins == 4 && $numero == 0){
            echo "<img src='images/yuan-obverse.jpg'</img>";
        }else if($type_of_coins == 4 && $numero == 1 ){
            echo "<img src='images/yuan-reverse.jpg'</img>";
        }

        //Francos suizos

        if($type_of_coins == 5 && $numero == 0){
            echo "<img src='images/franco-obverse.jpg'</img>";
        }else if($type_of_coins == 5 && $numero == 1 ){
            echo "<img src='images/franco-reverse.jpg'</img>";
        }

        //Pesos Colombianos
        if($type_of_coins == 6 && $numero == 0){
            echo "<img src='images/peso-obverse.jpg'</img>";
        }else if($type_of_coins == 6 && $numero == 1 ){
            echo "<img src='images/peso-reverse.jpg'</img>";
        }
    }
}
?>

</form>
</body>
</html>

```

*Documentacion Extra:*

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)

- [Documentación oficial de la estructura de control *if*](http://php.net/manual/es/control-structures.if.php)

- [Documentación oficial de la estructura de control *else*](http://php.net/manual/es/control-structures.else.php)

- [Documentación oficial del elemento de imagen *\<img>*](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img)

- [Documentación de la estructura de control switch](http://php.net/manual/es/control-structures.switch.php)

- [Documentación de la función *rand*](http://php.net/manual/es/function.rand.php)

- [Documentación funciones definidas en PHP](http://php.net/manual/es/functions.user-defined.php)

- [Devolver valores de una función PHP](http://php.net/manual/es/functions.returning-values.php)