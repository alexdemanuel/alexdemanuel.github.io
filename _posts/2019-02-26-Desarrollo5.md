---
layout: post
title:  "Desarrollo - JSON"
date:   2019-01-25 11:20:02 +0000
categories: desarrollo
---
# JSON

## Escribe un script que haga uso de la API de OpenWeatherMap y muestre la previsión metereológica de la ciudad que se indique en un formulario web.

- [Documentación función *json_decode*](http://php.net/manual/es/function.json-decode.php)
- [Documentación función *json_encode*](http://php.net/manual/es/function.json-encode.php)

*Para esta api usaremos 2 archivos, el index.php con el formulario para indicar la ciudad a la que deseamos saber el tiempo y esta nos redirigira al segundo archivo el cual recibirá la ciudad indicada (en caso de que la ciudad no exista o sea erronea dara un mensaje de error) y nos mostrara los datos sobre el tiempo en la ciudad solicitada*

Index.php

```bash
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Page Title</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" type="text/css" media="screen" href="main.css" />
    <script src="main.js"></script>
</head>
<body>

<form action="api.php" method="get">
    <div>
        <label for="ciudades">Ciudad:</label>
        <input type="text"id="ciudad" name="ciudad">

        <button type="submit">Enviar</button> 
            
    </div>

    
</body>
</html>
```

- Api.php

```bash

<?php

if(empty($_GET["ciudad"]) == 1){

    //echo "<h1> Error </h2>";
    //echo "<h2> Tiene que indicar el nombre de una ciudad</h2>";
    header('location: index.php');
    exit;

}else{
   

    $ciudad = $_GET["ciudad"];
    $appid = "2e1771d6989168058859fdd4b1b30d89";
    
    $url = "https://api.openweathermap.org/data/2.5/weather?q=".$ciudad."&appid=".$appid."&units=metric";
    
    $json = @file_get_contents($url); // el @ hace que no se muestre el warning
    $weather = json_decode($json);
    

    if($weather->cod !=200){
        echo "<h1> No se ha encontrado la ciudad deseada</h2>";
        exit;
}
    //para que te aparezca una imagen de como esta el cielo y la descripcion de este

    echo "<img src=\"http://openweathermap.org/img/w/".$weather->weather[0]->icon.".png\">";
    echo "<h2>".$weather->weather[0]->description."</h2>";
    
    //asi se accede a los apartados de los objetos que vamos a devolver en patalla
    echo "<table border=1>";

    echo "<tr>";
    echo "<td> Pais: ".$weather->sys->country."</td>";
    echo "</tr>";

    echo "<tr>";
    echo "<td> Ciudad: ".$weather->name."</td>";
    echo "</tr>";

    echo "<tr>";
    echo "<td> Lat: ".$weather->coord->lat."</td>";
    echo "</tr>";
    
    echo "<tr>";
    echo "<td> Lon: ".$weather->coord->lon."</td>";
    echo "</tr>";
    
    echo "<tr>";
    echo "<td> Temp: ".$weather->main->temp."</td>";
    echo "<tr>";
    
    echo "</tr>";
    echo "<td> humidity: ".$weather->main->humidity."</td>";
    echo "</tr>";
    
    echo "<tr>";
    echo "<td> Temp mínima: ".$weather->main->temp_min."</td>";
    echo "</tr>";
    
    echo "<tr>";
    echo "<td> Temp máxima: ".$weather->main->temp_max."</td>";
    echo "</tr>";
    echo "</table>";

}


?>
```






*Documentacion Extra:*

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)

- [Documentación oficial de la estructura de control *if*](http://php.net/manual/es/control-structures.if.php)

- [Documentación oficial de la estructura de control *else*](http://php.net/manual/es/control-structures.else.php)

- [Documentación oficial del elemento de imagen *\<img>*](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img)

- [Documentación de la estructura de control switch](http://php.net/manual/es/control-structures.switch.php)

- [Documentación de la función *rand*](http://php.net/manual/es/function.rand.php)
