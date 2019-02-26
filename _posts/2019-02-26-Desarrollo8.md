---
layout: post
title:  "Desarrollo - Objetos en PHP"
date:   2019-01-25 11:20:02 +0000
categories: desarrollo
---
#Introducción a Objetos en PHP

- [Documentación oficial sobre clases y objetos en PHP.](http://php.net/manual/es/language.oop5.php)
- [Introducción a la Programación Orientada a Objetos (POO) en PHP por Diego Lázaro.](https://diego.com.es/programacion-orientada-a-objetos-en-php)

```bash
<?php
//Creamos una clase
class Coche{

    //propiedades o variables
    
    private $color;  //aqui se le puede asignar un valor por defecto
    protected $potencia; // solo tiene acceso a el la clase en la que se encuentra y las clases que lo hereden
    public $marca;

    // metodos o funciones

    public function setColor($color){ //si la variable esta en privada asi se le puede dar un valor desde fuera del objeto (recomendado mas seguridad)
        $this->color = $color;
    }


    public function getColor(){
         echo "estoy en metodo getColor";
         echo $this->color; //con el this hace referencia a la variable que hay dentor del objeto
    }


}
// clase que hereda las propiedades y metodos de otra clase

class CocheDeLujo extends Coche{
    public function setPotencia($potencia){ //Accede a potencia que esta protected porque la esta heredando de la clase coche con el extended
        $this->potencia = $potencia;
    }
}

//creamos instancia (objeto) de la clase coche

//asi se pueden crear varios objetos de la clase coche
$Coche1 = new Coche();
$Coche2 = new Coche();

//Dar valor a la variable del objeto
$Coche1->color = "Naranja";
$Coche1->getColor();

$Coche2->setColor("Rojo");
$Coche2->getColor();
echo "El coche de toño es de color: ".$CocheTono->color; // aqui solo podemos acceder al color si la variable de la clase es publico
?>
```

## 1.Define una clase llamada Persona que cumpla los siguientes requisitos:
- Debe tener las siguientes propiedades privadas:
    - nombre
    - apellido1
    - apellido2
    - edad
- Debe tener un constructor que permita inicializar los valores de las propiedades.
- Define tener métodos públicos get y set para cada una de las propiedades.
- Debe incluir un método público llamado imprimir que muestre todas las propiedades del objeto.

Una vez definida la clase, relice dos instancias y utilice todos los métodos que ha creado


```bash
<?php

class Persona{
   private $nombre;
   private $apellido1;
   private $apellido2;
   private $edad;
    //Constructor                           //Lo de ="" es que en caso de que no se le asignen parametros se le asignaran esos
    public function __construct($nombre="", $apellido1="", $apellido2="", $edad=""){
        $this->nombre = $nombre;
        $this->apellido1 = $apellido1;
        $this->apellido2 = $apellido2;
        $this->edad = $edad;

    }


   //Nombre
   public function setNombre($nombre){
        $this->nombre = $nombre;
    }

    public function getNombre(){
        return $this->nombre;
    }

    //Apellido 1
    public function setApellido1($apellido1){ 
        $this->apellido1 = $apellido1;
    }

    public function getApellido1(){
        return $this->apellido1;
    }

    //Apellido 2
    public function setApellido2($apellido2){ 
        $this->apellido2 = $apellido2;
    }

    public function getApellido2(){
        return $this->apellido2;
    }

    //Edad
    public function setEdad($edad){ 
        $this->edad = $edad;
    }

    public function getEdad(){
        return $this->edad; 
    }

   public function imprimir(){
        echo " Nombre: ".$this->nombre;
        echo " Apellido 1: ".$this->apellido1;
        echo " Apellido 2: ".$this->apellido2;
        echo " Edad: ".$this->edad;
        echo "</br>";

   }

}

// Fuera de la clase
    $Persona1 = new Persona();
    $Persona2 = new Persona();
    $Persona3 = new Persona("Maria","Navarro", "Molero", "20"); //Los agrega en el orden que iindica la funcion constructor que es necesaria


    $Persona1->setNombre("Antonio");
    $Persona1->setApellido1("Lopez");
    $Persona1->setApellido2("Garrido");
    $Persona1->setEdad("20");

    // Una de las opciones para mostrar el valor deseado del objeto
   /* echo " Nombre: ".$Persona1->getNombre();
    echo " Apellido 1: ".$Persona1->getApellido1();
    echo " Apellido 2: ".$Persona1->getApellido2();
    echo " Edad: ".$Persona1->getEdad();
    */

    $Persona2->setNombre("Alejandro");
    $Persona2->setApellido1("De Manuel");
    $Persona2->setApellido2("Olmedo");
    $Persona2->setEdad("20");

    $Persona1->imprimir();
    echo "</br>";
    $Persona2->imprimir();


?>
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