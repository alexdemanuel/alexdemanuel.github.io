---
layout: post
title:  "Desarrollo - Introducción a PHP"
date:   2019-01-21 11:20:02 +0000
categories: desarrollo
---

# 1. Escribe un script PHP que muestre información sobre la configuración de PHP que hay en el servidor.

- [Documentacion oficial de la funcion phpinfo](http://php.net/manual/es/function.phpinfo.php)

*Resolución*
```bash
<?php
phpinfo()
?
```



# 2. Revise la documentación oficial de PHP para ver qué información podemos obtener de la variable superglobal *$_SERVER*. Escribe un script haciendo uso de la variable superglobal *$_SERVER* muestre lo siguiente:

- La dirección IP del servidor donde se está ejecutando el script.

- El nombre del host del servidor donde se está ejecutando el script.

- El software que está utilizando el servidor para servir el script.

- Información sobre el agente de usuario (User Agent) desde el que se está solicitando el script.

- La dirección IP del cliente que está solicitando el script.

[Documentación Oficial Variable superglobal *$_SERVER*](http://php.net/reserved.variables.server)


*Resolución*

```bash 

<?php

//muestra un array variables
print("<pre>");
print($_SERVER);
print("</pre>");

print("-------------");

//muestra arrays con la informacion de la variable
print("<pre>");
print_r($_SERVER);
print("</pre>");

?>
```

# 3. Revise la documentación oficial para conocer todas las variables superglobals que existen. Con ayuda de la función  print_r muestra el contenido de cada una de las variables superglobals.

- [Documentación oficial de las variables globales](http://php.net/manual/es/language.variables.superglobals.php)

*Resolución*

```bash
<?php

//Variable $_GLOBALS Nos muestra todas las variables del servidor
print("<pre>");
print("<h2>Variable \$GLOBALS</h2>");
print_r($GLOBALS);
print("</pre>");

print("-------------");

//Variable $_SERVER es un array que contiene información, tales como cabeceras, rutas y ubicaciones de script
print("<pre>");
print("<h2>Variable \$_SERVER</h2>");
print_r($_SERVER);
print("</pre>");

print("-------------");

//Variable $_GET Un array asociativo de variables pasado al script actual vía parámetros URL.
print("<pre>");
print("<h2>Variable \$_GET</h2>");
print_r($_GET);
print("</pre>");

print("-------------");

// Variable $_POST Nos muestra Variables POST(formularios) de HTTP
print("<pre>");
print("<h2>Variable \$_POST</h2>");
print_r($_POST);
print("</pre>");

print("-------------");

// Variable $_FILES Un array asociativo de elementos subidos al script en curso a través del método POST
print("<pre>");
print("<h2>Variable \$_FILES</h2>");
print_r($_FILES);
print("</pre>");

print("-------------");

// Variable $_COOKIE Una variable tipo array asociativo de variables pasadas al script actual a través de Cookies HTTP. 
print("<pre>");
print("<h2>Variable \$_COOKIE</h2>");
print_r($_COOKIE);
print("</pre>");

print("-------------");

// Variable $_SESSION Es un array asociativo que contiene variables de sesión disponibles 
print("<pre>");
print("<h2>Variable \$_SESSION</h2>");
print_r($_SESSION);
print("</pre>");

print("-------------");

// Variable $_REQUEST Un array asociativo que por defecto contiene el contenido de $_GET, $_POST y $_COOKIE.

print("<pre>");
print("<h2>Variable \$_REQUEST</h2>");
print_r($_REQUEST);
print("</pre>");

print("-------------");

// Variable $_ENV Una variable tipo array asociativo de variables pasadas al script actual a través del método del entorno.
print("<pre>");
print("<h2>Variable \$_ENV</h2>");
print_r($_ENV);
print("</pre>");

?>

```


# 4. Escribe un script que haga una redirección a una URL diferente.

*Resolución*

```bash
<?php
header('Location: https://example.com');
?>
```


*Documentación Extra:*


- [Documentación oficial de la funcion de red *header*](http://php.net/manual/es/function.header.php)

- [Documentación oficial de la funcion *print_r*](http://php.net/manual/es/function.print-r.php)

- [Repositorio GitHub](https://github.com/alexdemanuel/Practicas-PHP)