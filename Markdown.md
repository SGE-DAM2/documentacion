# MARKDOWN

### INDICE
1. [INTRODUCCIÓN](#introducción)
2. [ENCABEZADOS](#encabezados)
3. [PARRAFOS](#parrafos)
4. [LINEAS HORIZONTALES](#lineas-horizontales)
5. [FORMATEO DEL TEXTO](#formateo-del-texto)
   * [Negrita](#negrita)
   * [Cursiva](#cursiva)
   * [Cursiva y negrita](#cursiva-y-negrita)
   * [Tachado](#tachado)
   * [Citas](#citas)
   * [Superíndice](#superindice)
   * [Subíndice](#subindice)
6. [CÓDIGO](#código)
7. [LISTAS](#listas)
8. [IMÁGENES](#imágenes)

### INTRODUCCIÓN
Markdown es un lenguaje de marcado creado por John Gruber.

Este es un lenguaje mucho más sencillo e intuitivo a la hora de codificarlo frente a otros como por ejemplo html.

Es cierto que es un lenguaje que no admite excesivas florituras como puede suceder con html que si nos permite usando CSS y Javascript.

Este lenguaje es el lenguaje por excelencia usado para realizar documentación, sobre todo teniendo en cuenta el grado de integración con GitHub.

EL objetivo de este tutorial no es otro que el de hacer una breve introducción para que los alumnos puedan conocer sus bases y usarlo a la hora de documentar un proyecto.


### ENCABEZADOS 
Para realizar los encabezados tenemos que usar el símbolo \# delante del texto que conforme el encabezado.

Este nos permite hasta 6 niveles de encabezado de mayor a menor en función del número de \# que se encuentren delante del texto que conforma este.

Estos niveles son equivalentes a los \<h1>,\<h2>, \<h3>, \<h4>, \<h5> y \<h6> de html.


#### *EJEMPLO*
 ``` html
 ### Encabezado equivalente a un <h3>
 ```  


### PARRAFOS
Los parrafos los creamos simplemente introduciendo dos saltos de linea, vamos haciendo dos veces Intro.

Si quiero hacer saltos de linea dentro de un mismo parrafo, tengo que pulsar: *barra espaciadora (2 veces) y despues Intro (2 veces)*



### LINEAS HORIZONTALES
Para crear lineas horizontales cuyo principal cometido es separar secciones existen diferentes opciones, aunque el resultado es el mismo

* \***
* \___
* \---

#### *EJEMPLO*
***

### FORMATEO DEL TEXTO
Para formatear nuestro texto tenemos básicamente la opción de negrita y cursiva.

#### **NEGRITA** 
Como vemos hemos puesto en negrita el subtitulo, para lo que usamos \** rodeando aquello que queremos que se muestre en negrita.

#### *EJEMPLO*
 ```markdown
 **texto en negrita** 
 ```
---
#### *CURSIVA* 
Como vemos hemos puesto en cursiva el subtitulo, para lo que usamos \* rodeando aquello que queremos que se muestre en cursiva.

#### *EJEMPLO*
 ```markdown
*texto que se mostará en curiva*
```
---

#### *CURSIVA y NEGRITA* 
Puedo mezclar ambos para lo que usamos \*** rodeando aquello que queremos que se muestre en cursiva y negrita al mismo tiempo.

#### *EJEMPLO*
 ```markdown
***texto que se mostará en curiva y negrita***
```
---
#### *TACHADO* 

Para poder tachar un texto se rodea de ~~

```markdown
la palabra ~~error~~ está tachada
```
cuyo resultado es 

la palabra ~~error~~ está tachada

---
#### *CITAS* 

Para introducir citas lo que tenemos que hacer s usar \> al principio de la linea de esta.

#### *EJEMPLO*
>"No te preocupes si no funciona bien. Si todo estuviera correcto, serías despedido de tu trabajo"
*Ley de Mosher de la Ingeniería del Software*
---


#### SUPERINDICE
Para lograr esto uso.

```markdown
Hola<sup>2
```
#### *EJEMPLO*

Hola<sup>2

---

#### SUBINDICE
Para lograr esto uso.

```markdown
H<sub>2</sub>O  CO<sub>2</sub>
```
#### *EJEMPLO*

H<sub>2</sub>O  CO<sub>2</sub>

---

### *CÓDIGO*
Existe la posiblidad de introducir trozos de código y darles formato. 

Hay dos opciones a la hora de tratarlos
* En linea    
    Este consiste en usar \`(comilla invertida) para rodear la linea de código.
    
    `int edad = 34 //definición de variable edad; `
* En bloque
    Este nos permite introducir un bloque de código e indicarle el tipo de lenguaje usado para que lo formatee. Se usa \```(comilla invertida) para rodear la linea de código. El lenguaje se especifica a continuación de las \``` iniciales.

    ```bash
    #!/usr/bin/env bash
    # AUTOR: Luis A. Martín
    # OBJETIVO: Trabajar con estructuras condicionales, bucles y manejo de ficheros
    # ENUNCIADO: 5.	Realiza un script, tecleando el nombre de un usuario,
    # primero comprobamos si existe, y si existe, tenemos que visualizar si dicho
    # usuario está conectado o no. Si está conectado, nos mostrará también a qué hora se conectó.
    # Si no existe nos mostrará un mensaje diciendo el usuario no existe.

    salir="n" # Inicialización de variable para comprobar si sigo o no.

    until [[ $salir =~ (s|S) ]]; do
        read -p "Introduce el nombre del usuario:" usuario
        

        who | tr -s " " | grep "^[$usuario]" | cut -d" " -f4>hora
        if [ -s hora ]; then #Comprueba si está vacío
            echo "el usuario $usuario se conectó a las $(cat hora)"
        else
            echo "el usuario $usuario no está conectado"
        fi

        read -p "¿Desea salir del programa? s/n " salir
    done
    ```


---
### LISTAS
Existen dos tipos de listas
* Desordenadas
* Ordenadas

    Para agregar listas ordenadas en Markdown debes agregar un número seguido de un punto, un espacio y el elemento de la lista
    ```markdown
    1. primer elemento de la lista
    2. segundo elemento de la lista
    ````

* No ordenadas

    Para agregar listas no ordenadas en Markdown debes agregar un guion -, un signo más + o un asterisco *

    ```markdown
    * alubias
    * pasta de dientes
    ```  

* Anidadas
  Estas se producen cuando introducimos una lista dentro de otra. Podemos mezclar tipos.

    ```markdown
    1. Primer elemento
    2. Segundo elemento
       1. Elemento 2.1   
       2. Elemento 2.2
    3. Tercer elemento
    ```

### ENLACES
Para crear los enlaces es necesario envolver el texto a enlazar de [ ] y pegado a el y entre ( ) la dirección o URL a dónde saltar.

Existen diversos tipos de enlaces posibles en markdown.

* A una dirección de un sitio web.

    En este caso la codificación será algo como lo siguiente

    `[markdown](https://es.wikipedia.org/wiki/Markdown)`

    lo que genera este enlace a la wikipedia
    [markdown](https://es.wikipedia.org/wiki/Markdown)
    
* A una parte del documento

    En este caso debo de indicar el lugar a enlazar anteponiendo #. Es el método que hemos usado para el ínidce.

    `[ENCABEZADOS](#encabezados)`

    Lo que genera el salto a la sección llamada así
    [ENCABEZADOS](#encabezados)

* De forma directa

    Tenemos la posibiladad de realizar un enlace directamente rodeando el enlace directamente con < >

    Así por ejemplo puedo hacer un enlace directo a mi correo escribiendo `<luis.martinlanza@iesmiguelherrero.es>`

    <luis.martinlanza@iesmiguelherrero.es>
    
     o introducir directamente la dirección sin usar nada luis.martinlanza@iesmiguelherrero.es

    

Comentar que con los enlaces existen opciones como dar formato al enlace, por ejemplo poniendolo en negrita, usando la sintaxis ya conocida, o que puedo poner un título al enlace para que nos aparezca al pasar con el cursor or encima. Esto último se logra añadiendo la descripción entrecomillada al final, después del parentesis.

`[markdown](https://es.wikipedia.org/wiki/Markdown "Este es el enlace a lo recogido en la wikipedia de markdown")`

Que produce este enlace; prueba a poner encima el ratón.
[markdown](https://es.wikipedia.org/wiki/Markdown "Este es el enlace a lo recogido en la wikipedia de markdown")

Por último para cerrar la sección de los enlaces decir que existen lo que se llaman enlaces a referencias, que no son otra cosa que una mejor organización de los enlaces existentes en el documento y que van a facilitar una mayor legibilidad para los programadores.

Para explicarlo voy a poner un trozo de código

```markdown
página de la organización [GNU][1]

......
......


[1]:https://www.gnu.org/home.es.html "Este es el anlace a GNU"

```
Como ves en enlace tiene a su vez una referencia en este caso un número. Se suelen poner al final del documento todos los enlaces de esta manera, lo que nos permite una mayor organización.

El resultado es

página de la organización [GNU][1]

---
### IMÁGENES
El trabajo con imágenes en markdown se hace practicamente igual que los enlaces (no deja de ser un enlace a una dirección dónde se encuentra almacenada la imagen). la única diferencia respecto a la sintaxis vista es que tenemos que nateponer una ! delante de lo visto hasta ahora.


```markdown
![GNU](imagenes/GNU.jpeg "Logo de GNU")
```
Lo cual nos muestra como resultado

![GNU](imagenes/GNU.jpeg "Logo de GNU")

Podría hasta hacer que esta imagen sea un enlace a la página de GNU usando este código

```markdown
[![GNU](imagenes/GNU.png)](https://www.gnu.org/home.es.html "Logo de enlace a GNU")
```
Lo cual nos muestra como resultado

[![GNU](imagenes/GNU.png)](https://www.gnu.org/home.es.html "Logo de enlace a GNU")


---
### TABLAS 

Las tablas en markdown se realizan de una forma bastante rudimentaria, como si estuviesemos dibujando

Para agregar tablas Markdown debes definir las cabeceras de columna mediante al menos tres guiones --- que se situarán por debajo del texto de la cabecera. Para separar las diferentes cabeceras tendrás que usar un símbolo de tubería |

Veamos un ejemplo

```markdown

| MODULOS DE PRIMERO | MODULOS DE SEGUNDO |
| ---------- | ---------- |
|Programación | Acceso a datos  |
| Marcas| SGE |
| ......|.....
```

Con el siguiente resultado


| MODULOS DE PRIMERO | MODULOS DE SEGUNDO |
| ---------- | ---------- |
|Programación | Acceso a datos  |
| Marcas| SGE |
| ......|.....


Os dejo un enlace a un generador de tablas para diversos lenguajes de marcado

https://www.tablesgenerator.com/markdown_tables






[1]:https://www.gnu.org/home.es.html "Este es el anlace a GNU"
