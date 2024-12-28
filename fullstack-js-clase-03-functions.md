# CLASE JS 03 Functions

## 1. Ejercicio Funciones: Fx, parameters and return

Nos piden crear una función llamada getBkgColor para obtener el color de fondo de un elemento web. O sea debe buscar un elemento a partir de un selector (#id o .class) entregado y debe devolver el color de fondo del elemento.

## Clarificación de instrucciones y paso a paso

1. Crear elementos html

- Dos divs
- Un id único para cada ele (ele-1 y ele-2)
- Una clase común: .element
- Colores de fondo definidos mediante inline style (red y yellow).

2. Crear función getBkgColor

- Reciba com parametro un selector CSS (como un #id o .class).
- Usa este selector para buscar elemento en el DOM.
- Devuelva el color de fondo del elemento encontrado.

## Conocimientos de esta clase/ejercicio

### Definición de Función

Las funciones son conjuntos de instrucciones que podemos programar una vez y utilizarlas cada vez que necesitemos, a veces ocuparemos funciones creadas por otros, así como también bien frecuentemente tendremos que crear las nuestras.

---

### Diferencias entre parametros y argumentos

- Parámetro: Es la variable "de entrada" que defines al crear la función. Es como un "espacio reservado" que recibirá valores cuando llames a la función.
  Ejemplo:

`function getBkgColor(selector) //selector es el parametro{
    //bloque de código
}`

- Argumento: Es el valor real que proporcionas cuando llamas a la función. Este valor se asigna al parámetro.

`getBkgColor("#el-1"); // "#el-1" es el argumento.
`

---

Los terminos “argumentos” y “parámetros” son típicamente confundidos en los primeros pasos de un desarrollador. Su diferencia es el momento en el que se escriben, cuando estamos definiendo una función, el término que ocupamos es **_parámetros_**, y cuando estamos ejecutando una función, los valores que asignados entre los paréntesis se conocen como **_argumentos_**.

---

## Consejos para nombrar funciones

- La buena práctica más común que se recomienda seguir en cuanto al nombre de una función es agregar un verbo en infinitivo al comienzo del nombre, además se debe tratar de que el nombre representa específicamente el objetivo del bloque de código que representa.

```
function calcularPromedio(){
}
function getData(){
}
function registarUsuario(){}
```

## Funciones anónimas

- Una función anónima es como se indica, una función sin nombre, que son útiles para ser pasadas como argumento a otra función.

- Un caso muy frecuente de esto es justo al momento de añadir un Event Listener

```
btn = document.querySelector("button")

/* Ejemplo de uso Con función normal */

function alertar(){
  alert("hola")
}
btn.addEventListener("click", alertar)

/* Ejemplo de uso Con función anónima */

btn.addEventListener("click", function() {
      alert("hola")
});
```

Como vemos la sintaxis es la misma, la única diferencia es que definimos directamente la función al momento de llamar addEventListener.

**_Si vas a llamar una única vez a la función probablemente sea mejor utilizar una función anónima._**

## Funciones como argumentos

En Javascript es muy frecuente que una función reciba otra función como argumento.

```
function procesar(func, name) {
    console.log(func(name));
}
procesar(function(name) { return `Hola, ${name}`; }, "Rodrigo");
```

```
function procesar(func, name)

```

- Aquí estamos declarando una función llamada **_procesar_** que acepta dos parámetros:

  - func: Se espera que este parámetro sea una función.

  - name: Este parámetro es un string (o cualquier tipo de dato) que se pasará a la función func.

`console.log(func(name))`

- Dentro de la función procesar, estamos llamando a func y pasándole el valor de name como argumento.

- func(name) ejecuta la función que se le pasa como primer parámetro a procesar, y el resultado de esa ejecución se muestra en la consola con console.log().

```
procesar(function(name) { return `Hola, ${name}`; }, "Rodrigo");
```

- Aquí estamos llamando a la función procesar y pasando dos argumentos:

  - El primer argumento es una función anónima (sin nombre) que acepta un parámetro name y devuelve un string Hola, ${name}.
  - El segundo argumento es el string "Rodrigo", que es el valor que se pasará al parámetro name de la función anónima.

- Entonces, cuando procesar recibe estos argumentos, la función anónima es llamada con "Rodrigo" como valor de name, lo que resultará en el saludo "Hola, Rodrigo", que será mostrado en la consola.

Este concepto es útil cuando quieres ejecutar una tarea determinada después de un evento o cuando algo específico sucede. De ahí el uso común de funciones callback.

**_Este es un concepto muy importante cuando trabajas con eventos en JavaScript, porque generalmente necesitamos pasar una función como argumento, y esa función puede requerir parámetros específicos según el evento que ocurra. La forma correcta de hacerlo es usar funciones anónimas para asegurarnos de que podemos controlar la ejecución y los parámetros que se pasan a las funciones que queremos ejecutar en respuesta a eventos._**

---

## Expresión de función

Una expresión de función es cuando se define una función dentro de una variable. El ejemplo de función anónima es también una expresión de función.

```
//EJEMPLO EXPRESION DE FUNCION

      //Ejemplo ChatGPT//

      const suma = function (a, b) {
        return a + b;
      };

      alert(suma(78, 76));

      //Ejemplo Clase//

      alertar = function () {
        alert("HolaCTM!");
      };
      alertar();
```

---

## Arrow functions

Las funciones arrow son una forma alternativa de escribir expresiones de funciones o funciones anónimas utilizando una flecha => lo que permite escribirlas de forma mucho más resumida.

```
const multiplicar = (a, b) => a * b;
console.log(multiplicar(4, 5));  // 20
```

![Alt text](tipos_funciones-1.png)

## Scope

El scope (en español ámbito) es un concepto que explica desde donde podemos acceder a las variables que definimos.

En javascript hay 3 tipos de scopes:

- Global
- Función
- Bloque

**_La definicion de variables con las keywords var, let y const tiene diferentes tipos de scope._**

## Hoisting

Hoisting (en español alzar) es un mecanismo por el cual todas las declaraciones se alzan al principio del scope (global o función) de donde fueron definidas.
La implicancia de esto es que podemos utilizar funciones incluso antes de definirlas, por ejemplo el siguiente script funcionará correctamente

También es importante recordar que hay dos formas de crear funciones en JavaScript, a través de declaraciones de función (functions declarations) o expresiones de función (functions expressions)
En las expresiones de función no aplica el hoisting

El hoisting es el comportamiento de JavaScript de elevar las declaraciones de variables y funciones al principio del contexto de ejecución. Sin embargo, solo las declaraciones son elevadas, no las inicializaciones.

## Ejemplos declaración de función, expresión de función y arrow function

```
// Declaración de función

function saludar(name) {
    return `¡Hola, ${name}!`;
}

// Expresión de función

const despedir = function(name) {
    return `Adiós, ${name}`;
};

// Función de flecha

const saludarFlecha = (name) => `¡Hola, ${name}!`;

console.log(saludar("Rodrigo"));
console.log(despedir("Rodrigo"));
console.log(saludarFlecha("Rodrigo"));
```
