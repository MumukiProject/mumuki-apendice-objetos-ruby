## Referencia rápida del lenguaje JavaScript

El lenguaje JavaScript es utilizado ampliamente para construir software en todo el mundo, siendo una de las principales tecnologías de la Web. En Mumuki sólo usamos una muy pequeña parte del mismo, que listamos a continuación:

### Declaración de Funciones

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)

Las funciones en JavaScript se declaran mediante la _palabra clave_ `function`, y su cuerpo va entre llaves `{` y `}`:

```javascript
function nombreDeLaFuncion(parametro1, parametro2, parametro3) {
  return ...;
}
```

Toda función debe tener al menos un retorno, que se expresa mediante `return`.

### Operadores matemáticos

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)

```javascript
4 + 5
10 - 5
8 * 9
10 / 5
```

### Operadores lógicos

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)

```javascript
true && false
true || false
! false
```

### Comparaciones

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)

```javascript
// para cualquier tipo de dato
"hola" === "hola"
"hola" !== "chau"

// para números
4 >= 5
4 > 5
4 <= 5
4 < 5
```


### Alternativa Condicional

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)

Los `if`s en JavaScript encierran la condición entre paréntesis y su cuerpo entre llaves:

```javascript
if (hayPersonasEnEspera()) {
  llamarSiguientePersona();
}
```

Además, los `if`s pueden opcionalmente tener un `else`:

```javascript
if (hayPersonasEnEspera()) {
  llamarSiguientePersona();
} else {
  esperarSiguientePersona();
}
```

Por último, podemos combinar varios `if`s para tomar decisiones ante múltiples condiciones:

```javascript
if (hayPersonasEnEspera()) {
  llamarSiguientePersona();
} else if (elPuestoDebeSeguirAbierto()) {
  esperarSiguientePersona();
} else {
  cerrarPuesto();
}
```


### Variables

> A partir de la [Lección 3: Variables y procedimientos](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-variables-y-procedimientos)

Las variables nos permiten _recordar_ valores y se declaran mediante la palabra reservada `let` y se les da un valor inicial usando `=`:

```javascript
let pesosEnMiBilletera = 100;
let diasQueFaltanParaElVerano = 10;
```

La mismas se asignan mediante `=`:

```javascript
pesosEnMiBilletera = 65;
diasQueFaltanParaElVerano = 7;
```

En ocasiones las asignaremos usando el valor anterior:

```javascript
pesosEnMiBilletera = pesosEnMiBilletera * 2;
diasQueFaltanParaElVerano = diasQueFaltanParaElVerano - 1;
```

La asignación anterior se puede compactar combinando el signo `=` y la operación:

```javascript
pesosEnMiBilletera *= 2;
diasQueFaltanParaElVerano -= 1;
```

### Repetición indexada

> A partir de la [Lección 7: Recorridos](../../guides/mumukiproject/mumuki-guia-javascript-practica-de-listas-y-registros)

Las listas pueden ser _recorridas_, visitando y haciendo algo con cada uno de sus elementos. Para ello contamos con la estructura de control `for..of`, que encierra su generador
entre paréntesis (`(` y `)`) y su cuerpo entre llaves (`{` y `}`):

```javascript
let patrimoniosDeLaHumanidad = [
  {declarado: 1979, nombre: "Parque nacional Tikal", pais: "Guatemala"},
  {declarado: 1983, nombre: "Santuario histórico de Machu Picchu", pais: "Perú"}
  {declarado: 1986, nombre: "Parque nacional do Iguaçu", pais: "Brasil"},
  {declarado: 1995, nombre: "Parque nacional de Rapa Nui", pais: "Chile"},
  {declarado: 2003, nombre: "Quebrada de Humahuaca", pais: "Argentina"}
]


let cantidadPatrimoniosDeclaradosEnEsteSiglo = 0;
for (let patrimonio of patrimoniosDeLaHumanidad) {
  if (patrimonio.declarado >= 2000) {
    cantidadPatrimoniosDeclaradosEnEsteSiglo += 1;
  }
}
```


## Biblioteca simplificada

Dentro de Mumuki usamos una biblioteca de funciones inspirada en la que ya viene con JavaScript,
pero simplifiacada para que sea más sencilla y segura de usar. A continuación listamos las principales funciones que se
pueden usar, indicando el equivalente _real_ en JavaScript cuando corresponda.

### `longitud(unString)`

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)
>
> Versión simplificada de [`length`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/length)

Uso:

```javascript
ム longitud("hola")
4
```

### `convertirEnMayuscula(unString)`

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)
>
> Versión simplificada de [`toUpperCase`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/toUpperCase)

Convierte un `unString` en mayúsculas:

```javascript
ム convertirEnMayuscula("hola")
"HOLA"
```

### `comienzaCon(unString, otroString)`

> A partir de la [Lección 1: Funciones y tipos de datos](../../guides/flbulgarelli/fundamentos-javascript-funciones-tipos-de-datos)
>
> Versión simplificada de [`startsWith`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/startsWith)

Dice si `unString` empieza con `otroString`:

```javascript
ム comienzaCon("aprendiendo a programar", "aprendiendo")
true

ム comienzaCon("aprendiendo a programar", "aprend")
true

ム comienzaCon("aprendiendo a programar", "programar")
false

ム comienzaCon("aprendiendo a programar", "tomar el té")
false
```

### `imprimir(unString)`

> A partir de la [Lección 3: Variables y procedimientos](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-variables-y-procedimientos)
>
> Versión simplificada de [`console.log`](https://developer.mozilla.org/es/docs/Web/API/Console/log)

Imprime por pantalla `unString`:

```javascript
ム imprimir("¡estoy imprimiendo!")
¡estoy imprimiendo!
```

### `tirarDado()`

> A partir de la [Lección 3: Variables y procedimientos](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-variables-y-procedimientos)

Devuelve al azar un número entre 1 y 6:

```javascript
ム tirarDado()
5
ム tirarDado()
1
ム tirarDado()
2
```

### `listasIguales`

> A partir de la [Lección 5: Listas](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-vectores)


```javascript
ム listasIguales(unaLista, otraLista)

```

### `longitud(unaLista)`

> A partir de la [Lección 5: Listas](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-vectores)
>
>  * [`length` de listas](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array/length)

Nos dice cuan largo es `unaLista`:

```javascript
ム longitud([true, false, false, true])
4
ム longitud([5, 6, 3])
3
```


### `agregar(unaLista, unElemento)`

> A partir de la [Lección 5: Listas](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-vectores)
>
> Versión simplificada de [`push`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array/push)

Inserta `unElemento` al final de `unaLista`.
Este es un procedimiento que no devuelve nada pero modifica a `unaLista`:

```javascript
ム let cancionesFavoritas = ["La colina de la vida", "Zamba por vos"]
// agrega el elemento "Seminare" a la lista  cancionesFavoritas
ム agregar(cancionesFavoritas, "Seminare")
// ahora la lista tiene un elemento más:
ム cancionesFavoritas
["La colina de la vida", "Zamba por vos", "Seminare"]
```

### `remover(unaLista)`

> A partir de la [Lección 5: Listas](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-vectores)
>
> Versión simplificada de [`pop`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array/pop)

Quita el último elemento de unaLista.
Este es un procedimiento que no devuelve nada pero modifica a unaLista:

```javascript
ム let listaDeCompras = ["leche", "pan", "arroz", "aceite", "yerba"]
// removemos el último elemento
ム remove(listaDeCompras)
// la "yerba" ya no está en lista de compras
ム listaDeCompras
["leche", "pan", "arroz", "aceite"]
```

### `posicion(unaLista, unElemento)`


> A partir de la [Lección 5: Listas](../../guides/flbulgarelli/mumuki-guia-fundamentos-javascript-vectores)
>
> Versión simplificada de [`indexOf`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array/indexOf)

Nos dice en qué posición se encuentra `unElemento` dentro de `unaLista`.
Si el elemento no está en la lista, devuelve `-1`

```javascript
ム let premios = ["dani", "agus", "juli", "fran"]
ム posicion(premios, "dani")
0
ム posicion(premios, "juli")
2
ム posicion(premios, "feli")
-1
```
