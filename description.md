<ul>

<li><a title="" href="#referencia-rapida-del-lenguaje-ruby">El lenguaje Ruby</a>
<li><a title="" href="#conceptos-de-programacion-con-objetos">Conceptos de programación con objetos</a>
<ul>
<li><a title="" href="#objeto">Objeto</a></li>
<li><a title="" href="#ambiente">Ambiente</a></li>
<li><a title="" href="#envio-de-mensajes">Envío de mensajes</a></li>
<li><a title="" href="#definicion-de-objetos">Definición de objetos</a></li>
<li><a title="" href="#definicion-de-metodos">Definición de métodos</a></li>
<li><a title="" href="#interfaz">Interfaz</a></li>
<li><a title="" href="#asignacion">Asignación</a></li>
<li><a title="" href="#self"><code>self</code></a></li>
<li><a title="" href="#responsabilidad-y-delegacion">Responsabilidad y delegación</a></li>
<li><a title="" href="#atributos">Atributos</a></li>
<li><a title="" href="#estado">Estado</a></li>
<li><a title="" href="#accessors">Accessors</a></li>
<li><a title="" href="#encapsulamiento">Encapsulamiento</a></li>
<li><a title="" href="#convenciones-para-la-nominacion-de-metodos">Convenciones para la nominación de métodos</a></li>
<li><a title="" href="#alternativa-condicional">Alternativa Condicional</a></li>
<li><a title="" href="#polimorfismo">Polimorfismo</a></li>
<li><a title="" href="#referencias">Referencias</a></li>
<li><a title="" href="#colecciones">Colecciones</a></li>
<li><a title="" href="#bloques-de-codigo">Bloques de código</a></li>
<li><a title="" href="#clases-e-instancias">Clases e instancias</a></li>
<li><a title="" href="#herencia">Herencia</a></li>
<li><a title="" href="#redefinicion">Redefinición</a></li>
<li><a title="" href="#clases-abstractas">Clases abstractas</a></li>
<li><a title="" href="#super"><code>super</code></a></li>
<li><a title="" href="#excepciones">Excepciones</a></li>
</ul>
</li>

<li><a title="" href="#operadores">Operadores</a>
<ul>
<li><a title="" href="#operadores-matematicos">Operadores matemáticos</a></li>
<li><a title="" href="#operadores-logicos">Operadores lógicos</a></li>
<li><a title="" href="#comparaciones">Comparaciones</a></li>
</ul>
</li>

<li><a title="" href="#metodos-usuales">Métodos usuales</a>
<ul>
<li><a title="" href="#numeroabs"><code>numero.abs</code></a></li>
<li><a title="" href="#numerotimes-bloque"><code>numero.times bloque</code></a></li>
<li><a title="" href="#stringupcase"><code>string.upcase</code></a></li>
<li><a title="" href="#stringsize"><code>string.size</code></a></li>
<li><a title="" href="#numeroeven"><code>numero.even?</code></a></li>
<li><a title="" href="#objetoequal-otro_objeto"><code>objeto.equal? otro_objeto</code></a></li>
<li><a title="" href="#coleccionpush-elemento"><code>coleccion.push elemento</code></a></li>
<li><a title="" href="#colecciondelete-elemento"><code>coleccion.delete elemento</code></a></li>
<li><a title="" href="#coleccioninclude-elemento"><code>coleccion.include? elemento</code></a></li>
<li><a title="" href="#coleccionsize"><code>coleccion.size</code></a></li>
<li><a title="" href="#coleccionselect-bloqueconcondicion"><code>coleccion.select bloque_con_condicion</code></a></li>
<li><a title="" href="#coleccionfind-bloqueconcondicion"><code>coleccion.find bloque_con_condicion</code></a></li>
<li><a title="" href="#coleccionall-bloqueconcondicion"><code>coleccion.all? bloque_con_condicion</code></a></li>
<li><a title="" href="#coleccionmap-bloque"><code>coleccion.map bloque</code></a></li>
<li><a title="" href="#coleccioncount-bloqueconcondicion"><code>coleccion.count bloque_con_condicion</code></a></li>
<li><a title="" href="#coleccionsum-bloque"><code>coleccion.sum bloque</code></a></li>
<li><a title="" href="#coleccioneach-bloque"><code>coleccion.each bloque</code></a></li>
<li><a title="" href="#clasenew"><code>Clase.new</code></a></li>
</ul>
</li>

</ul>
  
<h2 id="referencia-rapida-del-lenguaje-ruby">El lenguaje Ruby</h2>

Ruby es un lenguaje de Programación Orientada a Objetos gratis y de código abierto creado en Japón. Su sintaxis amigable lo hace muy popular sobre todo en el desarrollo web; de hecho una gran parte de la Plataforma Mumuki está desarrollada en este lenguaje.

<h2 id="conceptos-de-programacion-con-objetos">Conceptos de programación con objetos</h2>

<h3 id="objeto">Objeto y ambiente</h3>

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

Los objetos son entes computacionales con los que interactuaremos para resolver problemas. Estos objetos "viven"en un ambiente:

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado/master/assets/pepita-energia-100.png" width="300" />

En este ambiente podemos ver a los objetos `Pepita`, `90` y `100`. 

<h3 id="envio-de-mensajes">Envío de mensajes</h3>

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

La manera de interactuar con los objetos es a través del envío de mensajes haciendo `objeto.mensaje`:

```ruby
ム Pepita.volar!
ム Pepita.comer! 20
```

En este caso `Pepita` es el objeto al cual le enviamos:

* el mensaje `volar!` que no recibe argumentos;
* y el mensaje `comer!` con el argumento `20`.

<h3 id="definicion-de-objetos">Definición de objetos</h3>

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

La definición de objetos en Ruby comienza anteponiendo `module` antes del nombre y finaliza con `end`.

```ruby
module Pepita
end

module Norita
end
```

<h3 id="definicion-de-metodos">Definición de métodos</h3>

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Para que un objeto entienda un mensaje es necesario crear un método dentro del mismo. La definición de los métodos comienzan con `def` y, al igual que en la declaración de objetos, finaliza con `end`. En el caso de los métodos creados dentro de un `module` es necesario anteponer al nombre `self.`. En caso que nuestro método reciba parámetros debemos ponerlos entre paréntesis separados por coma.

```ruby
module Pepita
    def self.cantar!
    end

    def self.volar!(distancia)
    end

    def self.comer!(cantidad, comida)
    end
end
```

<h3 id="interfaz">Interfaz</h3>

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

Interfaz es el conjunto de mensajes que entiende un objeto. En el ejemplo anterior, la interfaz de `Pepita` está compuesta por los mensajes `cantar!`, `volar!` y `comer!`.

<img src="http://www.plantuml.com/plantuml/png/7St13S8m34RXkwTmD-a8R12vwGzOYftASP40iJjgRf_UvQqZ9VAqHkg9k4i5tt1e2d-9cU68Xyh5AfuIosGtH6dTjj3FBA_U90gyL8rwjZuM-X4zTGV3ZdopmJR485hX-_Nx0m00" width="165" />

<h3 id="asignacion">Asignación</h3>

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Para asignarle un valor a una variable utilizamos `=`.

```ruby
numero_favorito = 8
color_favorito = "Violeta"
```
<a id="self"></a>
### `self`

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Es la manera que tiene un objeto de enviarse mensajes a sí mismo; en estos casos `self` es el objeto receptor del mensaje.

```ruby
module Gaby
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

<h3 id="responsabilidad-y-delegacion">Responsabilidad y delegación</h3>

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

La responsabilidad, en la programación con objetos, está relacionada con qué objeto debería resolver las determinadas partes de nuestro problema. Si un objeto no es responsable de hacer algo lo debe delegar en el correspondiente.

<h3 id="atributos">Atributos</h3>

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

Los atributos son objetos que me permiten representar una característica de otro objeto. Un objeto conoce a todos sus atributos por lo que puede enviarles mensajes. Los atributos se escriben anteponiendo `@` y si bien no es necesario inicializarlos, hasta que no lo hagamos valdrán `nil`.

```ruby
module Pepita
    @energia = 100

    def self.cantar!
    end

    def self.ciudad=(una_ciudad)
        @ciudad = una_ciudad
    end

    def self.volar!(distancia)
        @energia = @energia - distancia * 2
    end

    def self.comer!(cantidad, comida)
    end
end
```

En este caso `@energia` es un atributo de `Pepita` que:

* `@energia` tiene un valor inicial de `100`;
* cuando `Pepita` recibe el mensaje `volar!` disminuye su `@energia` el doble de la distancia recorrida.
* `@ciudad` vale `nil` hasta que no le enviemos a `Pepita` el mensaje `ciudad=` con una ciudad como argumento.

<h3 id="estado">Estado</h3>

> A partir de la [Lección 2: Definiendo objetos: métodos y estado](../../guides/mumukiproject/mumuki-guia-ruby-definiendo-objetos-metodos-y-estado)

El estado de un objeto es el conjunto de atributos que posee. Todos los atributos son privados, para acceder o modificar los atributos de un objeto es necesario definir métodos dentro del mismo.

<h3 id="accessors">Accessors</h3>

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

Los accessors son métodos que me permiten acceder o modificar el estado de un objeto y son conocidos como getters y setters respectivamente.

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

<h3 id="encapsulamiento">Encapsulamiento</h3>

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

El encapsulamiento es la recomendable práctica de minimizar la exposición del estado de nuestros objetos. Para ello definiremos solo aquellos _accessors_ que sean indispensables; tengamos en cuenta que no siempre vamos a querer definir _getters_ y/o _setters_ para todos los atributos de cada objeto. Veamos un ejemplo:

```ruby
module AutoDeFabi
	@patente = "AAA 111"
	@nafta = 200
	@color = "rojo"

	def self.patente
		@patente
	end

	def self.color=(un_color)
		@color = un_color
	end

	def self.cargar!(cantidad)
		@nafta += cantidad
	end
end

module Fabi
	def self.pintar_auto!(un_color)
		AutoDeFabi.color = un_color
	end

	def self.cargar_nafta!(una_cantidad)
		AutoDeFabi.cargar! una_cantidad
	end
end
```

En este caso `AutoDeFabi`:

* tiene definido un _getter_ para su atributo `@patente`. Sin embargo, no define un _setter_ ya que tiene sentido que pueda decir su patente pero que no se pueda modificar externamente;
* tiene un _setter_ para su atributo `@color` ya que el objeto `Fabi` puede modificarlo directamente;
* no define ningún _accessor_ para su atributo `@nafta` ya que en caso que `Fabi` desee cargar nafta le enviará el mensaje `cargar!` a `AutoDeFabi`.


<h3 id="convenciones-para-la-nominacion-de-metodos">Convenciones para la nominación de métodos</h3>

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

    def self.volar!(distancia)
        @energia = @energia - distancia * 2
    end
    
    def self.cansada?
      @energia < 10
    end
end
```

Si bien nuestro código funcionará correctamente en caso de no respetar estas convenciones, será menos comprensible para otras personas que lo lean.

<h3 id="alternativa-condicional">Alternativa Condicional</h3>

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

La alternativa condicional en Ruby comienza con `if` seguido por la condición y termina con `end`:

```ruby
if Pepita.aburrida?
  Pepita.volar! 10
end
```

En caso de contar con un rama de `else`, `end` va al final del mismo:

```ruby
if Norita.hambrienta?
    Norita.comer! 10, "alpiste"
else
    Norita.volar! 15
end
```

A diferencia de otros lenguajes, en Ruby podemos hacer `elsif` en caso de tener un `if` dentro de un `else`:

```ruby
if Cleo.cansada?
    Cleo.descansar!
elsif Cleo.aburrida?
    Cleo.leer!
else
    Cleo.trabajar!
end
```

<h3 id="polimorfismo">Polimorfismo</h3>

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)

El polimorfismo en objetos es la capacidad que tiene un objeto de poder enviarle el mismo mensaje indistintamente a objetos diferentes. Estos objetos deben entender este mensaje más allá de cómo este definido el método asociado al mismo, es decir, dos o más objetos son polimórficos cuando comparten una interfaz. Para que estemos ante un caso de polimorfismo es necesaria la presencia de al menos tres objetos: uno que envíe el mensaje y dos distintos que puedan entenderlo. Veámoslo en un ejemplo:

Supongamos que `Agus` puede realizar llamadas por celular enviandole un mensaje `llamar!` con un parámetro minutos a su atributo `@celular`: 

```ruby
module Agus
	def self.celular=(un_celular)
		@celular = un_celular
	end

	def self.realizar_llamada!(minutos)
		@celular.llamar! minutos
	end
end
```

El celular que `Agus` utiliza puede ser tanto su `CelularPersonal` como su `CelularLaboral`:

```ruby
module CelularPersonal
	@saldo = 200

	def self.llamar!(minutos)
		@saldo -= minutos
	end
end

module CelularLaboral
	@minutos_consumidos = 0

	def self.llamar!(minutos)
		@minutos_consumidos += minutos
	end
end
```

Gracias a que `CelularPersonal` y `CelularLaboral` son polimórficos para el mensaje `llamar!`, `Agus` puede realizar llamadas sin tener que verificar qué celular está utilizando. 

<h3 id="referencias">Referencias</h3>

> A partir de la [Lección 4: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)

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
module Guille
    @paginas_leidas

    def self.leer!(libro)
        @paginas_leidas = @paginas_leidas + libro.cantidad_de_paginas
    end
end
```
<h3 id="colecciones">Colecciones</h3>

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)

Las colecciones son objetos que contienen referencias a otros objetos. Un tipo de colección son las _listas_, las cuales se escriben entre corchetes (`[]`) y permiten tener objetos repetidos con un orden determinado dentro de ellas:

``` ruby
ム libros = [Fundacion, Socorro, Elevacion, Kriptonita, Socorro]
```

Otro tipo de colecciones muy común son los _sets_, los cuales a diferencia de las listas no pueden tener elementos repetidos y sus elementos no tienen un orden determinado:

``` ruby
ム numeros_aleatorios = [1,27,8,7,8,27,87,1]
ム numeros_aleatorios
=> [1,27,8,7,8,27,87,1]
ム numeros_aleatorios.to_set
=> #<Set: {1, 27, 8, 7, 87}>
```

<h3 id="bloques-de-codigo">Bloques de código</h3>

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)

Los bloques son objetos que representan un mensaje o una secuencia de envíos de mensajes, sin ejecutar, lista para ser evaluada cuando corresponda. 

``` ruby
ム anio_actual = 2021
ム anio_nuevo = proc { anio_actual = anio_actual + 1 }
```

Estos bloques de código pueden recibir parámetros escritos entre `||` separados por comas.

``` ruby
ム saludador = proc { |saludo, nombre| saludo + " " + nombre + ", que lindo día para programar, ¿no?" }
```

Dentro de cada bloque podemos usar y enviarle mensajes tanto a los parámetros del bloque (`saludo` y `nombre`) como a las variables declaradas fuera del mismo (`anio_actual`).

Por último, para ejecutar el código dentro del bloque debemos enviarle el mensaje `call` con los argumentos correspondientes.

``` ruby
ム anio_nuevo.call
=> 2022

ム saludador.call("Hola", "Jor")
=> "Hola Jor, que lindo día para programar, ¿no?"
```

<h3 id="clases-e-instancias">Clases e instancias</h3>

> A partir de la [Lección 6: Clases e Instancias](../../guides/mumukiproject/mumuki-guia-ruby-clases-e-instancias)

Las clases son objetos que sirven de moldes para crear nuevos objetos que tienen el mismo comportamiento.

Por ejemplo, si tuvieramos dos perros representados con los objetos `Firulais` y `Stimpy`:

```ruby
class Firulais
    @energia = 200

    def self.jugar!(un_tiempo)
        @energia -= un_tiempo
    end

    def recibir_duenio!
        @energia += 100
    end
end

class Stimpy
    @energia = 300

    def self.jugar!(un_tiempo)
        @energia -= un_tiempo
    end

    def recibir_duenio!
        @energia += 100
    end
end
```

Podemos ver que tienen el mismo comportamiento. Para poder solucionar esta repetición podríamos crear la clase `Perro`:

```ruby
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

El método `initialize` de las clases permite especificar cómo se inicializan las instancias de una clase. En este método declararemos los valores iniciales de los atributos. Por último para crear nuestros objetos debemos hacer:

``` ruby
firulais = Perro.new 200
stimpy = Perro.new 300
```

Estos nuevos objetos creados a partir de una clase (`firulais` y `stimpy`) son instancias de la misma. Es importante tener en cuenta que:

* Todo instancia pertenece a una y sólo una clase.
* No se puede cambiar la clase de una instancia en tiempo de ejecución.

<h3 id="herencia">Herencia</h3>

> A partir de la [Lección 7: Herencia](../../guides/mumukiproject/mumuki-guia-ruby-herencia)

Cuando dos objetos repiten lógica, creamos una clase con el comportamiento en común. En el caso que dos clases repitan lógica deberíamos crear una nueva clase a la cual llamamos superclase. A esta nueva clase llevaremos los métodos repetidos y haremos que las clases originales hereden de ella. Estas subclases que heredan de la superclase solo contendrán su comportamiento particular.

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

<h3 id="redefinicion">Redefinición</h3>

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

<h3 id="clases-abstractas">Clases abstractas</h3>

> A partir de la [Lección 7: Herencia](../../guides/mumukiproject/mumuki-guia-ruby-herencia)

Las clases abstractas son clases que no se desea instanciar. Sirven para abstraer la lógica repetida de otras clases pero no las usaremos como molde de otros objetos. En contraposición, aquellas que sí instanciaremos son las llamadas clases concretas. En el ejemplo anterior `Mascota` es una clase abstracta mientras que `Gato` y `Perro` son clases concretas.

<a id="super"></a>
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

<h3 id="excepciones">Excepciones</h3>

> A partir de la [Lección 8: Excepciones](../../guides/mumukiproject/mumuki-guia-ruby-excepciones)

Una excepción es una indicación de que algo salió mal. Cuando lanzamos una excepción provocamos un error explícito que interrumpe el flujo de nuestro programa. La excepción no solo aborta el método en el cual la lanzamos sino también la ejecución de todos los métodos de la cadena de envío de mensajes pero no descarta los cambios realizados anteriormente; es por este motivo que es importante saber en qué momento debemos hacerlo. Por último, para lanzar excepciones utilizaremos `raise` con un mensaje expresivo para entender por qué se interrumpió el flujo.

```ruby
ム raise "No se puede realizar esta acción"
No se puede realizar esta acción (RuntimeError)
```

<h2 id="operadores">Operadores</h2>

<h3 id="operadores-matematicos">Operadores matemáticos</h3>

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

```ruby
8 + 7
32 - 9
2 * 3
4 / 2
```

<h3 id="operadores-logicos">Operadores lógicos</h3>

> A partir de la [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

```ruby
true && false
true || false
! false
```

<h3 id="comparaciones">Comparaciones</h3>

> A partir de la  [Lección 1: Objetos y mensajes](../../guides/mumukiproject/mumuki-guia-ruby-objetos-y-mensajes)

```ruby
Pepita == Norita
"ser" != "estar"
7 >= 5
7 > 5
7 <= 5
7 < 5
```

<h2 id="metodos-usuales">Metodos usuales</h2>

A lo largo del capítulo "Programación con Objetos" utilizamos algunos métodos en la resolución de ejercicios. A continuación te los listamos en el orden que aparecen.

<a id="numeroabs"></a>
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

<a id="numerotimes-bloque"></a>
### `numero.times bloque`

> A partir de la [Lección 3: Polimorfismo y encapsulamiento](../../guides/mumukiproject/mumuki-guia-ruby-polimorfismo)
>
> Ejecuta el código del `bloque` tantas veces como diga `numero`.

```ruby
ム Pepita.energia = 5

ム 3.times { Pepita.energia = Pepita.energia * 2 }

ム Pepita.energia
=> 40
```

<a id="stringupcase"></a>
### `string.upcase`

> A partir de la [Lección 4: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
>
> Retorna un nuevo string con todos los caracteres de `string` en mayúsculas.

```ruby
ム "libro".upcase
=> "LIBRO"
```

<a id="stringsize"></a>
### `string.size`

> A partir de la [Lección 4: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
>
> Retorna la cantidad de caracteres de `string`.

```ruby
ム "camino".size
=> 6
```

<a id="numeroeven"></a>
### `numero.even?`

> [Lección 4: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
>
> Nos permite saber si `numero` es par.

```ruby
ム 8.even?
=> true

ム 7.even?
=> false
```

<a id="objetoequal-otro_objeto"></a>
### `objeto.equal? otro_objeto`

> A partir de la [Lección 4: Referencias](../../guides/mumukiproject/mumuki-guia-ruby-referencias)
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

<a id="coleccionpush-elemento"></a>
### `coleccion.push elemento`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Agrega `elemento` a `coleccion`.

```ruby
ム numeros_de_la_suerte = [8, 7, 42]

ム numeros_de_la_suerte.push 9

ム numeros_de_la_suerte
=> [8, 7, 42, 9]
```

<a id="colecciondelete-elemento"></a>
### `coleccion.delete elemento`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Remueve `elemento` de `coleccion`.

```ruby
ム numeros_de_la_suerte = [8, 7, 42]

ム numeros_de_la_suerte.delete 7

ム numeros_de_la_suerte
=> [8, 42]
```

<a id="coleccioninclude-elemento"></a>
### `coleccion.include? elemento`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Nos permite saber si `elemento` pertenece a `coleccion`.

```ruby
ム [25, 87, 776].include? 8
=> true

ム [25, 87, 776].include? 9
=> false
```
<a id="coleccionsize"></a>
### `coleccion.size`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna la cantidad de elementos dentro de `coleccion`.

```ruby
ム ["hola", "todo", "bien", "por", "acá"].size
=> 5
```

<a id="coleccionselect-bloqueconcondicion"></a>
### `coleccion.select bloque_con_condicion`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna una nueva colección con los elementos de `coleccion` que cumplan con la condición de `bloque_con_condicion`. Este método no tiene efecto sobre `coleccion`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].select { |un_numero| un_numero > 5 }
=> [7, 11, 13]
```

<a id="coleccionfind-bloqueconcondicion"></a>
### `coleccion.find bloque_con_condicion`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna el primer el elemento de `coleccion` que cumpla con la condición de `bloque_con_condicion`. Si ningún elemento cumple la condición nos devuelve `nil`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].find { |un_numero| un_numero > 15 }
=> nil
```

<a id="coleccionall-bloqueconcondicion"></a>
### `coleccion.all? bloque_con_condicion`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Nos permite saber si todos los elementos de `coleccion` cumplen con la condición de `bloque_con_condicion`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].all? { |un_numero| un_numero > 5 }
=> false

ム [1, 2, 3, 5, 7, 11, 13].all? { |un_numero| un_numero < 20 }
=> true
```

<a id="coleccionmap-bloque"></a>
### `coleccion.map bloque`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna una nueva colección con el resultado de ejecutar el código de `bloque` por cada elemento de `coleccion`.

```ruby
ム [1, 2, 3, 4, 5].map { |un_numero| un_numero * 2 }
=> [2, 4, 6, 8, 10]
```

<a id="coleccioncount-bloqueconcondicion"></a>
### `coleccion.count bloque_con_condicion`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna cuántos elementos de `coleccion` cumplen con la condición de `bloque_con_condicion`.

```ruby
ム [1, 2, 3, 5, 7, 11, 13].count { |un_numero| un_numero > 3 }
=> 4
```

<a id="coleccionsum-bloque"></a>
### `coleccion.sum bloque`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Retorna la suma de los valores obtenidos al ejecutar el código de `bloque` en cada elemento de `coleccion`.

```ruby
ム juegos_de_mesa = [Ajedrez, Damas, Ludo]

ム juegos_de_mesa.sum { |un_juego| un_juego.cantidad_de_piezas }
=> 60 # 32 del ajedrez + 24 de las damas + 4 del ludo
```

<a id="coleccioneach-bloque"></a>
### `coleccion.each bloque`

> A partir de la [Lección 5: Colecciones](../../guides/mumukiproject/mumuki-guia-ruby-colecciones)
>
> Ejecuta el código de bloque por cada elemento de `coleccion`. El método `each` no retorna una nueva colección sino que tiene efecto sobre la original.

```ruby
ム golondrinas = [Pepita, Norita, Mercedes]

ム golondrinas.each { |una_golondrina| una_golondrina.comer_lombriz! } # Hace que cada golondrina de la colección coma lombriz.
```

<a id="clasenew"></a>
### `Clase.new`

> A partir de la [Lección 6: Clases e Instancias](../../guides/mumukiproject/mumuki-guia-ruby-clases-e-instancias)
>
> Crea y retorna una nueva instancia de `Clase`.

```ruby
ム guitarra = Instrumento.new
ム piano = Instrumento.new
```
