## Referencia rápida del lenguaje Ruby

Ruby es un lenguaje de Programación Orientada a Objetos gratis y de código abierto creado en Japón. Su sintaxis amigable lo hace muy popular sobre todo en el desarrollo web; de hecho una gran parte de la Plataforma Mumuki está desarrollada en este lenguaje.

### Objeto

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

Los objetos son entes computacionales con los que interactuaremos para resolver problemas.

### Ambiente

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

El ambiente es el lugar donde "viven" los objetos con los cuales podemos interactuar.

### Envío de mensajes

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

La manera de interactuar con los objetos es a través del envío de mensajes haciendo `objeto.mensaje`:

```ruby
ム Pepita.volar!
ム Pepita.comer!(20)
```

En este caso `Pepita` es el objeto al cual le enviamos:

* el mensaje `volar!` que no recibe argumentos;
* y el mensaje `comer!` con el argumento `20`.

### Interfaz

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

Interfaz es el conjunto de mensajes que entiende un objeto.

### Declaración de objetos

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

La declaración de objetos en Ruby comienza anteponiendo `module` antes del nombre y finaliza con `end`.

```ruby
module Pepita
end

module Norita
end
```

### Definición de métodos

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Para que un objeto entienda un mensaje es necesario crear un método dentro del mismo. La definición de los métodos comienzan con `def` y, al igual que en la declaración de objetos, finaliza con `end`. En el caso de los métodos creados dentro de un `module` es necesario anteponer al nombre `self.`. En caso que nuestro método reciba parámetros debemos ponerlos entre paréntesis separados por coma.

```ruby
module Pepita
    def self.cantar!
    end

    def self.volar! (distancia)
    end

    def self.comer! (cantidad, comida)
end
```

### Asignación

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Para asignarle un valor a una variable utilizamos `=`.

```ruby
numero_favorito = 8
color_favorito = "Violeta"
```

### `self`

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Es la manera que tiene un objeto de enviarse mensajes a sí mismo; en estos casos `self` es el objeto receptor del mensaje.

```ruby
module Paco
    @esta_alegre = false

    def self.escuchar_musica!
        @esta_alegre = true
        self.bailar!
    end

    def self.bailar!
        # No es importante esta definición
    end
end
```

### Responsabilidad y delegación

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

La responsabilidad, en la programación con objetos, está relacionada con qué objeto debería resolver las determinadas partes de nuestro problema. Si un objeto no es responsable de hacer algo lo debe delegar en el correspondiente.

### Atributo

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Los atributos son objetos que me permiten representar una característica de otro objeto. Un objeto conoce a todos sus atributos por lo que puede enviarles mensajes. Los atributos se escriben anteponiendo `@`.

```ruby
module Pepita
    @energia = 100

    def self.cantar!
    end

    def self.volar! (distancia)
        @energia = @energia - distancia * 2
    end

    def self.comer! (cantidad, comida)
end
```

En este caso `@energia` es un atributo de `Pepita` que:

* tiene un valor inicial de `100`;
* cuando `Pepita` recibe el mensaje `volar!` disminuye el doble de la distancia recorrida.

### Estado

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

El estado de un objeto es el conjunto de atributos que posee. Todos los estados son privados, para acceder o modificar los atributos de un objeto es necesario definir métodos dentro del mismo.

### Accesors

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

Los accesors son métodos que me permiten acceder o modificar el estado de un objeto y son conocidos como getters y setters respectivamente.

```ruby
module Pepita
    @energia = 100

    def self.energia
        @energia
    end

    def self.energia=(nueva_energia)
        @energia = nueva_energia
    end
end
```

## Convenciones para la nominación de métodos

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

A la hora de ponerle un nombre a los métodos que definimos hay que tener en cuenta ciertas convenciones de Ruby, es decir, algunos acuerdos entre la comunidad de personas que programan en este lenguaje:

* Los nombres de métodos que producen un cambio de estado deben finalizar con `!`;
* Los nombres de métodos que retornan un valor booleano deben finalizar con `?`;
* Los getters llevan el mismo nombre que el atributo que retornan pero sin el `@`.
* Los setters llevan el mismo nombre que el atributo que modifican, pero sin el `@` y con `=` al final.

```ruby
module Pepita
    @energia = 100
    
    def self.energia
        @energia
    end

    def self.energia=(nueva_energia)
        @energia = nueva_energia
    end

    def self.volar! (distancia)
        @energia = @energia - distancia * 2
    end
    
    def self.esta_cansada?
      @energia < 10
    end
end
```

### Alternativa Condicional

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

La alternativa condicional en Ruby comienza con `if` seguido por la condición y termina con `end`:

```ruby
if Pepita.esta_aburrida?
  Pepita.volar! (10)
end
```

En caso de contar con un rama de `else`, `end` va al final del mismo:

```ruby
if Norita.tiene_hambre?
    Norita.comer! (10, "alpiste")
else
    Norita.volar! (15)
end
```

A diferencia de otros lenguajes, en Ruby podemos hacer `elsif` en caso de tener un `if` dentro de un `else`:

```ruby
if Cleo.esta_cansada?
    Cleo.descansar!
elsif Cleo.esta_aburrida?
    Cleo.leer!
else
    Cleo.trabajar!
end
```

### Polimorfismo

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

El polimorfismo en objetos es la capacidad que tiene un objeto de poder enviarle el mismo mensaje indistintamente a objetos distintos. Estos objetos deben entender este mensaje más allá de cómo este definido el método asociado al mismo. Para que estemos ante un caso de polimorfismo es necesaria la presencia de al menos tres objetos: uno que envíe el mensaje y dos distintos que puedan entenderlo.

### Encapsulamiento

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

Una buena práctica es definir solo aquellos accesors que sean indispensables para minimizar la exposición del estado de nuestros objetos. A esta práctica la llamamos encapsulamiento.

### Colecciones

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)

Las colecciones son objetos que contienen otros objetos. Un tipo de colección son las listas, las cuales se escriben entre corchetes (`[]`) y permiten tener objetos repetidos con un orden determinado dentro de ellas.

``` ruby
ム libros = [Fundacion, Socorro, Elevacion, Kriptonita]
```

### Bloques de código

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)

Los bloques son objetos que representan un mensaje o una secuencia de envíos de mensajes, sin ejecutar, lista para ser evaluada cuando corresponda. 

``` ruby
ム anio_actual = 2021
ム anio_nuevo = proc { anio_actual = anio_actual + 1}
```

Estos bloques de código pueden recibir parámetros escritos entre `||` separados por comas.

``` ruby
ム saludador = proc { |saludo, nombre| saludo + " " + nombre + ", que lindo día para programar, ¿no?"}
```

Para ejecutar el código dentro del bloque debemos enviarle el mensaje `call` con los argumentos correspondientes.

``` ruby
ム anio_nuevo.call
=> 2022

ム saludador.call("Hola", "Jor")
=> "Hola Jor, que lindo día para programar, ¿no?"
```

### Referencias

> A partir de la [Lección 5: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)

Cuando le enviamos un mensaje a un objeto, en realidad no lo conocemos directamente sino que lo hacemos a través de etiquetas llamadas referencias. Algunos ejemplos de referencias y envío de mensajes a través de las mismas son:

* las variables

``` ruby
dia = "domingo"
dia.upcase
```

* las referencias implícitas

``` ruby
"insomnio".upcase
            ^
            +-- Acá hay una referencia implícita al objeto "insomnio"
```

* los objetos bien conocidos (los que declaramos con `module`)

``` ruby
module Pepita
    def self.cantar!
    end
end

Pepita.cantar!
```

* los atributos

``` ruby
module Pepita
    @ciudad = GeneralLasHeras

    def self.coordenadas
        @ciudad.coordenadas
    end
end
```

* los parámetros

``` ruby
module Gra
    @paginas_leidas

    def self.leer! (libro)
        @paginas_leidas = @paginas_leidas + libro.cantidad_de_paginas
    end
end
```

### Clases e instancias

> A partir de la [Lección 6: Clases e Instancias](../../guides/mumukiproject/mumuki-guia-ruby-clases-e-instancias)

Las clases son objetos que sirven de moldes para crear nuevos objetos que tienen el mismo comportamiento. Estos nuevos objetos creados a partir de una clase son instancias de la misma. Es importante tener en cuenta que:

* Todo instancia pertenece a una y sólo una clase.
* No se puede cambiar la clase de una instancia en tiempo de ejecución.

### Constructores

> A partir de la [Lección 6: Clases e Instancias](../../guides/mumukiproject/mumuki-guia-ruby-clases-e-instancias)

El método `initialize` de las clases permite especificar cómo se inicializan las instancias de una clase. En este método declararemos los valores iniciales de los atributos.

``` ruby
class Persona
    def initialize(peso)
        @peso = peso
        @dientes = 0
    end
end

elena = Persona.new(480)
fausto = Persona.new(390)
```

### Herencia

> A partir de la [Lección 7: Herencia](../../guides/mumukiproject/mumuki-guia-ruby-herencia)

Cuando dos objetos repiten lógica, creamos una clase con el comportamiento en común. En el caso que dos clases repitan lógica debemos crear una nueva clase, a la cual llamamos superclase, que la contenga, definiendo en cada una de las clases iniciales, llamadas subclases, sólo lo particular de cada una.

Por ejemplo si tuvieramos:

```ruby
class Gato
    def initialize(energia)
        @energia = energia
    end

    def jugar!(un_tiempo)
	    @energia -= un_tiempo
    end
    
    def recibir_duenio!
        @energia -= 10
    end
end

class Perro
    def initialize(energia)
        @energia = energia
    end

    def jugar!(un_tiempo)
	    @energia -= un_tiempo
    end
    
    def recibir_duenio!
        @energia += 100
    end
end
```

Podríamos crear la clase `Mascota`:

```ruby
class Mascota
    def initialize(energia)
        @energia = energia
    end

    def jugar!(un_tiempo)
	    @energia -= un_tiempo
    end
    
    def recibir_duenio!
    end
end
```

Por último es necesario hacer que las clases `Gato` y `Perro` hereden de `Mascota` utilizando `<`:

```ruby
class Gato < Mascota
    def recibir_duenio!
        @energia -= 10
    end
end

class Perro < Mascota
    def recibir_duenio!
        @energia += 100
    end
end
```

En nuestra nueva jerarquía `Mascota` es una superclase de la cual heredan las subclases `Gato` y `Perro`.

### Redefinición

> A partir de la [Lección 7: Herencia](../../guides/mumukiproject/mumuki-guia-ruby-herencia)

La redefinición de métodos de una superclase nos permite modificar en las subclases el comportamiento definidio originalmente. Por ejemplo si en una subclase `Gallina` de `Mascota` quisieramos redefinir el método `jugar!` lo haríamos de esta forma:

```ruby
class Gallina < Mascota
    def jugar!(un_tiempo)
	    @energia -= 5
    end

    def recibir_duenio!
        @energia *= 2
    end
end
```

### Clases abstractas

> A partir de la [Lección 7: Herencia](../../guides/mumukiproject/mumuki-guia-ruby-herencia)

Las clases abstractas son clases que no se desea instanciar. Sirven para abstraer la lógica repetida de otras clases pero no la usaremos como molde de otros objetos. Aquellas que si instanciaremos son las llamadas clases concretas. En el ejemplo anterior `Mascota` es una clase abstracta mientras que `Gato` y `Perro` son clases concretas.

### Métodos abstractos

> A partir de la [Lección 7: Herencia](../../guides/mumukiproject/mumuki-guia-ruby-herencia)

Las clases abstractas especifican que métodos deben implementar aquellas clases que heredan de ella. Estos métodos, llamados abstractos, no tienen comportamiento y el mismo está definido en sus subclases en métodos concretos. Por ejemplo, en la clase `Mascota` tenemos el método concreto `jugar!` y el método abstracto `recibir_duenio!`.

### `super`

> A partir de la [Lección 7: Herencia](../../guides/mumukiproject/mumuki-guia-ruby-herencia)

`super` nos permite redefinir un método pero sólo agregar una parte nueva a la funcionalidad, reutilizando la lógica común que está definida en la superclase. Al utilizar `super` en el método de una subclase, se evalúa el método con el mismo nombre de su superclase.

Por ejemplo:

```ruby
class Pichicho < Perro
    def recibir_duenio!
        super
        self.ladrar!
    end
end
```

### Excepciones

> A partir de la [Lección 8: Excepciones](../../guides/mumukiproject/mumuki-guia-ruby-excepciones)

Una excepción es una indicación de que algo salió mal. Cuando lanzamos una excepción provocamos un error explícito que interrumpe el flujo de nuestro programa. La excepción no solo aborta el método en el cual la lanzamos sino también la ejecución de todos los métodos de la cadena de envío de mensajes pero no descarta los cambios realizados anteriormente; es por este motivo que es importante saber en qué momento debemos lanzarla. Por último, el mensaje con el cual lanzamos la excepción debe ser expresivo para entender por qué se interrumpió el flujo.

### Operadores matemáticos

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

```ruby
8 + 7
32 - 9
2 * 3
4 / 2
```

### Operadores lógicos

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

```ruby
true && false
true || false
! false
```

### Comparaciones

> A partir de la  [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

```ruby
Pepita == Norita
"ser" != "estar"
7 >= 5
7 > 5
7 <= 5
7 < 5
```

## Método usuales

A lo largo del capítulo "Programación con Objetos" utilizamos algunos métodos en la resolución de ejercicios. A continuación te los listamos en el orden que aparecen.

### `numero.abs`

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)
>
> Permite obtener el valor absoluto de un número.

```ruby
ム 8.abs
=> 8

ム (-8).abs
=> 8

ム (3 - 7).abs
=> 4
```

### `numero.times bloque`

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)
>
> Ejecuta el código del `bloque` tantas veces como diga `numero`.

```ruby
ム Pepita.energia=(5)

ム 3.times { Pepita.energia=(Pepita.energia * 2)}

ム Pepita.energia
=> 40
```

### `coleccion.push elemento`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Agrega `elemento` a `coleccion`.

```ruby
ム numeros_de_la_suerte = [8, 7, 42]

ム numeros_de_la_suerte.push 9

ム numeros_de_la_suerte
=> [8, 7, 42, 9]
```

### `coleccion.delete elemento`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Remueve `elemento` de `coleccion`.

```ruby
ム numeros_de_la_suerte = [8, 7, 42]

ム numeros_de_la_suerte.delete 7

ム numeros_de_la_suerte
=> [8, 42]
```

### `coleccion.include? elemento`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Nos permite saber si `elemento` pertenece a `coleccion`.

```ruby
ム [25, 87, 776].include? 8
=> true

ム [25, 87, 776].include? 9
=> false
```
### `coleccion.size`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna la cantidad de elementos dentro de `coleccion`.

```ruby
ム ["hola", "todo", "bien", "por", "acá"].size
=> 5
```

### `coleccion.select bloqueConCondicion`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna una nueva colección con los elementos de `coleccion` que cumplan con la condición de `bloqueConCondicion`. Este método no tiene efecto sobre `coleccion`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].select { |un_numero| un_numero > 5 }
=> [7, 11, 13]
```

### `coleccion.find bloqueConCondicion`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna el primer el elemento de `coleccion` que cumpla con la condición de `bloqueConCondicion`. Si ningún elemento cumple la condición nos devuelve `nil`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].find { |un_numero| un_numero > 15 }
=> nil
```

### `coleccion.all? bloqueConCondicion`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Nos permite saber si todos los elementos de `coleccion` cumplen con la condición de `bloqueConCondicion`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].all? { |un_numero| un_numero > 5 }
=> false

ム [1, 2, 3, 5, 7, 11, 13].all? { |un_numero| un_numero < 20 }
=> true
```

### `coleccion.map bloque`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna una nueva colección con el resultado de ejecutar el código de `bloque` por cada elemento de `coleccion`.

```ruby
ム [1, 2, 3, 4, 5].map { |un_numero| un_numero * 2 }
=> [2, 4, 6, 8, 10]
```

### `coleccion.count bloqueConCondicion`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna cuántos elementos de `coleccion` cumplen con la condición de `bloqueConCondicion`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].count { |un_numero| un_numero > 3 }
=> 4
```

### `coleccion.sum bloque`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna la suma de los valores obtenidos al ejecutar el código de `bloque` en cada elemento de `coleccion`.

```ruby
ム juegos_de_mesa = [Ajedrez, Damas, Ludo]

ム juegos_de_mesa.sum { |un_juego| un_juego.cantidad_de_piezas }
=> 60 # 32 del ajedrez + 24 de las damas + 4 del ludo
```

### `coleccion.each bloque`

> A partir de la [Lección 4: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Ejecuta el código de bloque por cada elemento de `coleccion`. El método `each` no retorna una nueva colección sino que tiene efecto sobre la original.

```ruby
ム golondrinas = [Pepita, Norita, Mercedes]

ム golondrinas.each { |una_golondrina| una_golondrina.comer_lombriz! } # Hace que cada golondrina de la colección coma lombriz.
```

### `string.upcase`

> A partir de la [Lección 5: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
>
> Retorna un nuevo string con todos los caracteres de `string` en mayúsculas.

```ruby
ム "libro".upcase
=> "LIBRO"
```

### `string.size`

> A partir de la [Lección 5: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
>
> Retorna la cantidad de caracteres de `string`.

```ruby
ム "camino".size
=> 6
```

### `numero.even?`

> [Lección 5: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
>
> Nos permite saber si `numero` es par.

```ruby
ム 8.even?
=> true

ム 7.even?
=> false
```

### `objeto.equal? otro_objeto`

> A partir de la [Lección 5: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
>
> Nos permite saber si `objeto` y `otro_objeto` son referencias que apuntan a exactamente el mismo objeto.

```ruby
ム un_string = "lamparita"
ム otro_string = un_string

ム un_string.equal? "lamparita"
=> false

ム un_string.equal? otro_string
=> true
```

### `Clase.new`

> A partir de la [Lección 6: Clases e Instancias](../../guides/mumukiproject/mumuki-guia-ruby-clases-e-instancias)
>
> Crea y retorna una nueva instancia de `Clase`.

```ruby
ム guitarra = Instrumento.new
ム piano = Instrumento.new
```

### `raise mensaje` 

> A partir de la [Lección 8: Excepciones](../../guides/mumukiproject/mumuki-guia-ruby-excepciones)
>
> Lanza una excepción con `mensaje`.

```ruby
ム raise "Se rompió todo"
Se rompió todo (RuntimeError)
```
