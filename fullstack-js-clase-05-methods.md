# Clase 05 Array methods

# Índice

- [Qué son los métods de arrays](#qué-son-los-métodos-de-arrays)
- [Push, Unshift, Splice](#push-unshift-y-splice-en-javascript)
- [Shift, Splice, Pop](#shift-splice-pop-eliminar-elementos-de-un-array-en-javascript)
- [Includes](#método-includes)
- [Lenght](#lenght)
- [forEach](#foreach)
- [Map](#método-map-en-javascript)
- [Concat](#método-concat-en-javascript)

## Qué son los métodos de arrays

Los métodos de los arrays en JavaScript son funciones integradas que permiten realizar diversas operaciones sobre los arreglos (arrays). Estas operaciones incluyen agregar, eliminar, buscar, modificar elementos, o transformar el contenido de un array, entre otras.

Un método de un array es simplemente una función que está asociada al objeto Array en JavaScript. Estas funciones se utilizan para interactuar con los elementos del array y facilitar tareas comunes.

Por ejemplo:

```javascript
let numeros = [1, 2, 3];
numeros.push(4); // Agrega un elemento al final del array
console.log(numeros); // [1, 2, 3, 4]
```

### Principales categorías de métodos

#### Agregar o eliminar elementos:

push: Agrega elementos al final.
unshift: Agrega elementos al inicio.
pop: Elimina el último elemento.
shift: Elimina el primer elemento.
splice: Agrega, reemplaza o elimina elementos en una posición específica.

#### Buscar o acceder a elementos:

indexOf: Devuelve la posición de un elemento.
includes: Comprueba si un elemento está en el array.
find: Encuentra el primer elemento que cumple una condición.
filter: Devuelve un nuevo array con elementos que cumplen una condición.

#### Transformar o modificar el array:

map: Crea un nuevo array aplicando una función a cada elemento.
sort: Ordena los elementos del array.
reverse: Invierte el orden de los elementos.

#### Combinar o dividir arrays:

concat: Combina dos o más arrays.
slice: Devuelve una copia de una parte del array.
join: Convierte los elementos en una cadena.
split: Convierte una cadena en un array (aunque este método es de cadenas, se usa mucho con arrays).

#### Reducir o procesar todos los elementos:

reduce: Procesa los elementos para generar un único valor (suma, concatenación, etc.).

## push, unshift y splice en JavaScript (agregar elementos)

### 1. `push`

- **Qué hace:**  
  Agrega uno o más elementos al final de un arreglo y devuelve la nueva longitud del arreglo.

- **Sintaxis:**

  ```javascript
  array.push(elemento1, elemento2, ..., elementoN);
  ```

  ```javascript let frutas = ['manzana', 'plátano'];
  frutas.push("naranja", "uva");
  console.log(frutas); // ['manzana', 'plátano', 'naranja', 'uva']
  ```

### 2. unshift

Qué hace:
Agrega uno o más elementos al inicio de un arreglo y devuelve la nueva longitud del arreglo.

Sintaxis:

```javascript
array.unshift(elemento1, elemento2, ..., elementoN);
```

```javascript
let colores = ["azul", "verde"];
colores.unshift("rojo", "amarillo");
console.log(colores); // ['rojo', 'amarillo', 'azul', 'verde']
```

### 3. splice

Qué hace:
Cambia el contenido de un arreglo eliminando, reemplazando o agregando elementos en una posición específica.

Sintaxis:

```javascript
array.splice(indice, cantidadAEliminar, elemento1, elemento2, ..., elementoN);
```

indice: Posición inicial donde se aplicarán los cambios.
cantidadAEliminar: Número de elementos a eliminar desde indice.
elemento1, elemento2, ...: Elementos a agregar en la posición indicada (opcional).

Ejemplo 1: Eliminar elementos

```javascript
let numeros = [1, 2, 3, 4, 5];
numeros.splice(2, 2); // Elimina 2 elementos desde el índice 2
console.log(numeros); // [1, 2, 5]
```

Ejemplo 2: Reemplazar elementos

```javascript
let animales = ["perro", "gato", "pez"];
animales.splice(1, 1, "tigre"); // Reemplaza 1 elemento en el índice 1
console.log(animales); // ['perro', 'tigre', 'pez']
```

Ejemplo 3: Agregar elementos sin eliminar

```javascript
let ciudades = ["Santiago", "Lima", "Buenos Aires"];
ciudades.splice(1, 0, "Bogotá", "Quito"); // Agrega sin eliminar
console.log(ciudades); // ['Santiago', 'Bogotá', 'Quito', 'Lima', 'Buenos Aires']
```

Comparación rápida

### Comparación rápida de métodos de arrays

| Método    | Agrega elementos      | Elimina elementos | Reemplaza elementos |
| --------- | --------------------- | ----------------- | ------------------- |
| `push`    | Al final              | No                | No                  |
| `unshift` | Al inicio             | No                | No                  |
| `splice`  | En cualquier posición | Sí                | Sí                  |

[Volver al índice](#índice)

## Shift, splice, pop (eliminar elementos de un array en JavaScript)

JavaScript ofrece varios métodos para eliminar elementos de un array. Cada uno tiene un propósito específico dependiendo de la posición del elemento que deseas eliminar.

1. Shift
   Elimina el primer elemento de un array y devuelve ese elemento. Esto reduce la longitud del array en 1.

Sintaxis:

```javascript
let frutas = ["manzana", "naranja", "pera"];
let eliminado = frutas.shift();
console.log(frutas); // ["naranja", "pera"]
console.log(eliminado); // "manzana"
```

2. splice

Elimina elementos de un array en una posición específica. También puede usarse para reemplazar o agregar elementos.

Sintaxis:

```javascript
array.splice(inicio, cantidad);
```

inicio: Índice donde comenzar a eliminar.

cantidad: Número de elementos a eliminar.

Ejemplo:

```javascript
let frutas = ["manzana", "naranja", "pera"];
let eliminados = frutas.splice(1, 1);
console.log(frutas); // ["manzana", "pera"]
console.log(eliminados); // ["naranja"]
```

3. pop
   Elimina el último elemento de un array y lo devuelve. Esto reduce la longitud del array en 1.

Sintaxis:

```
array.pop();
```

Ejemplo:

```javascript
let frutas = ["manzana", "naranja", "pera"];
let eliminado = frutas.pop();
console.log(frutas); // ["manzana", "naranja"]
console.log(eliminado); // "pera"
```

### Comparación de métodos para eliminar elementos de un array

| Método   | Elimina elementos                    | Devuelve                     | Modifica el array | Descripción                                           |
| -------- | ------------------------------------ | ---------------------------- | ----------------- | ----------------------------------------------------- |
| `shift`  | El primer elemento                   | El primer elemento eliminado | Sí                | Elimina el primer elemento de un array.               |
| `pop`    | El último elemento                   | El último elemento eliminado | Sí                | Elimina el último elemento de un array.               |
| `splice` | Elementos en una posición específica | Elementos eliminados (array) | Sí                | Elimina elementos en cualquier posición especificada. |

[Volver al índice](#índice)

## Método includes

El método includes se utiliza para verificar si un array contiene un elemento específico. Es una forma sencilla y directa de comprobar la existencia de un valor en el array.

### Características principales de includes:

Devuelve un valor booleano (true o false).

Realiza una búsqueda estricta (usa comparación estricta ===).

Es útil para búsquedas rápidas en arrays o strings.

Sintaxis:

```
array.includes(valor, desde);

```

valor: El elemento que deseas buscar.

desde (opcional): El índice desde donde comenzar la búsqueda. Si no se especifica, comienza desde el inicio.

```javascript
let frutas = ["manzana", "naranja", "pera"];

console.log(frutas.includes("naranja")); // true
console.log(frutas.includes("uva")); // false
```

Ejemplo con el parámetro desde:

Puedes indicar desde qué índice empezar la búsqueda.

```javascript
let numeros = [1, 2, 3, 4, 5, 2];

console.log(numeros.includes(2)); // true (2 está en el índice 1)
console.log(numeros.includes(2, 2)); // true (2 está en el índice 5)
console.log(numeros.includes(2, 6)); // false (2 no está después del índice 6)
```

Comparación estricta (===):

El método includes utiliza comparación estricta, por lo que distingue entre tipos de datos.

```javascript
let valores = [1, "1", true];

console.log(valores.includes(1)); // true (número 1)
console.log(valores.includes("1")); // true (string "1")
console.log(valores.includes(true)); // true (booleano true)
console.log(valores.includes(false)); // false (booleano false no está)
```

Uso práctico

1. Validar si un elemento está en una lista:

```javascript
let permisos = ["admin", "editor", "viewer"];

if (permisos.includes("admin")) {
  console.log("Tienes permisos de administrador.");
} else {
  console.log("No tienes permisos de administrador.");
}
```

2. Evitar duplicados antes de agregar:

```javascript
let numeros = [1, 2, 3];

if (!numeros.includes(4)) {
  numeros.push(4);
}

console.log(numeros); // [1, 2, 3, 4]
```

[Volver al índice](#índice)

## Lenght

El método length no es un método en sí mismo, sino una propiedad de los arrays (y strings). Esta propiedad devuelve el número de elementos en un array o la cantidad de caracteres en un string.

Características principales de length:

Devuelve un valor numérico: Indica la cantidad de elementos en un array o caracteres en un string.

Es de solo lectura: No puedes cambiar el valor de length directamente (aunque puedes modificar el array o string para que cambie automáticamente).

Es dinámico: Si añades o eliminas elementos de un array, la propiedad length se actualiza automáticamente.

Sintaxis

```javascritp
array.length;
```

### Ejemplos con arrays:

1. Obtener la longitud de un array:

```javascript
let frutas = ["manzana", "naranja", "pera"];
console.log(frutas.length); // 3
```

2. Añadir un elemento y ver cómo cambia length:

```javascript
let frutas = ["manzana", "naranja"];
console.log(frutas.length); // 2

frutas.push("pera");
console.log(frutas.length); // 3
```

3. Modificar el length directamente:

```javascript
let frutas = ["manzana", "naranja", "pera"];
frutas.length = 2; // Elimina los elementos después del índice 1
console.log(frutas); // ["manzana", "naranja"]
```

_La propiedad length es muy poderosa y permite modificar la longitud del array directamente. Aquí estás haciendo lo siguiente:_

_Inicializas el array frutas con tres elementos: ["manzana", "naranja", "pera"]._

_Cambia la propiedad length a 2, lo que significa que el array se truncará hasta el índice 1. Los elementos después del índice 1 (en este caso, "pera") serán eliminados._

_Imprimes el array después de modificar su longitud. El resultado es ["manzana", "naranja"], ya que el array ahora solo tiene los dos primeros elementos._

Comportamiento de length con arrays y objetos:

En un array, length devuelve el número de elementos que contiene.

En un string, length devuelve el número de caracteres.
length es sensible a los elementos vacíos: Si un array tiene "huecos" (elementos vacíos), se cuentan en la longitud.

```javascript
let arrayConHuecos = [1, , 3]; // Elemento vacío en el índice 1
console.log(arrayConHuecos.length); // 3
```

### Comparación del uso de `length` en arrays y strings

| Tipo                | ¿Qué mide?                           | Ejemplo                            | Resultado |
| ------------------- | ------------------------------------ | ---------------------------------- | --------- |
| `length` en arrays  | El número de elementos del array     | `let arr = [1, 2, 3]; arr.length;` | 3         |
| `length` en strings | El número de caracteres en el string | `let str = "Hola"; str.length;`    | 4         |

[Volver al índice](#índice)

## forEach

El método .forEach() es un método de los arreglos en JavaScript que ejecuta una función dada una vez por cada elemento de un arreglo, en orden.

Es utilizado para realizar acciones sobre los elementos del arreglo sin modificar el arreglo original ni retornar un nuevo valor.

A diferencia de otros métodos que devuelven un nuevo arreglo (como .map() o .filter()), .forEach() simplemente ejecuta una acción en cada elemento y no devuelve nada.

Sintaxis

```javascript
array.forEach(function (element, index, array) {
  // código a ejecutar por cada elemento
});
```

function(element): Función que se ejecuta por cada elemento del arreglo. Recibe como parámetro el elemento actual.

index (opcional): El índice del elemento actual dentro del arreglo.
array (opcional): El arreglo original sobre el cual se está iterando.

Características:

No devuelve nada: El método .forEach() siempre devuelve undefined. Si se desea obtener un nuevo arreglo basado en los elementos del original, se debe usar .map().

No puede ser interrumpido: No se puede usar break, continue ni return dentro de .forEach() para controlar la iteración.

Ideal para efectos secundarios: Se utiliza generalmente cuando se desea realizar efectos secundarios (como actualizar el DOM, imprimir en consola, modificar variables externas, etc.), pero no para transformar o filtrar datos.

Ejemplo:

```javascript
const estaciones = ["Verano", "Otoño", "Invierno", "Primavera"];

estaciones.forEach(function (estacion) {
  console.log(estacion);
});
```

[Volver al índice](#índice)

## Método `map` en JavaScript

El método .map nos permite generar un arreglo nuevo a partir de aplicar una función a cada elemento de un arreglo,
map no modifica el arreglo original.

```javascript
 const valores = [200, 100, 500, 300, 250]
 const nuevos_valores = valores.map(x => 2* x)
 console.log(nuevos_valores) /* [400, 200, 1000, 600, 500
```

**¿Cuando usar .forEach y cuando .map?**

.forEach es útil cuando queremos hacer algo de inmediato con cada dato iterado, por ejemplo mostrarlo en pantalla o agregarlo al html. .map cuando queremos transformar los datos para seguir trabajando con ellos.

El método `map` se utiliza para **crear un nuevo array transformando cada elemento del array original** mediante una función que defines. No modifica el array original.

#### Definición

```javascript
array.map(callback(currentValue, index, array), thisArg);
```

- **`callback`**: Una función que se ejecuta en cada elemento del array. Recibe:
  - **`currentValue`**: El elemento actual.
  - **`index`** _(opcional)_: El índice del elemento actual.
  - **`array`** _(opcional)_: El array original.
- **`thisArg`** _(opcional)_: Un valor que se puede usar como `this` dentro del callback.

#### Características clave

1. Devuelve un nuevo array del mismo tamaño que el original.
2. El array original no se modifica.
3. Se utiliza para transformar datos, no para filtrar o iterar sin crear un nuevo array.

---

#### Ejemplos prácticos

#### **1. Multiplicar cada número por 2**

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map((num) => num * 2);

console.log(doubled); // [2, 4, 6, 8]
console.log(numbers); // [1, 2, 3, 4] (el array original no cambia)
```

---

#### **2. Convertir un array de cadenas a mayúsculas**

```javascript
const fruits = ["manzana", "pera", "uva"];
const uppercased = fruits.map((fruit) => fruit.toUpperCase());

console.log(uppercased); // ['MANZANA', 'PERA', 'UVA']
```

---

#### **3. Extraer una propiedad de objetos**

```javascript
const users = [
  { id: 1, name: "Ana" },
  { id: 2, name: "Luis" },
  { id: 3, name: "María" },
];
const names = users.map((user) => user.name);

console.log(names); // ['Ana', 'Luis', 'María']
```

---

#### **4. Crear un array de objetos con nuevos datos**

```javascript
const prices = [100, 200, 300];
const pricesWithTax = prices.map((price) => ({
  price: price,
  priceWithTax: price * 1.19,
}));

console.log(pricesWithTax);
/*
[
  { price: 100, priceWithTax: 119 },
  { price: 200, priceWithTax: 238 },
  { price: 300, priceWithTax: 357 }
]
*/
```

---

#### **5. Agregar índices a los elementos**

```javascript
const letters = ["a", "b", "c"];
const indexed = letters.map((letter, index) => `${index}: ${letter}`);

console.log(indexed); // ['0: a', '1: b', '2: c']
```

---

#### Cuándo usar `map`

- Cuando necesitas transformar los datos de un array sin modificar el original.
- Cuando deseas mantener el tamaño del array.

[Volver al índice](#índice)

## filter

El método filter() en JavaScript se utiliza para crear un nuevo arreglo con todos los elementos que pasen una prueba determinada, la cual se define en una función callback. Este método no modifica el arreglo original.

Sintaxis

```javascript
let nuevoArreglo = arreglo.filter(funciónDePrueba);
```

arreglo: El arreglo sobre el cual se ejecuta el filtro.

funciónDePrueba: Una función que define la condición que debe cumplir cada elemento para ser incluido en el nuevo arreglo. Esta función recibe tres parámetros: el valor actual del elemento, el índice del elemento y el arreglo original.

Ejemplos:

Filtrar números mayores que 10:

```javascript
const numeros = [5, 12, 8, 130, 44];
const mayoresQue10 = numeros.filter((num) => num > 10);
console.log(mayoresQue10); // [12, 130, 44]
```

[Volver al índice](#índice)

## Método `concat()` en JavaScript

El método `concat()` en JavaScript se utiliza para **combinar dos o más arrays** en un nuevo array. No modifica los arrays originales, sino que devuelve un nuevo array con los elementos concatenados.

#### **Sintaxis**

```javascript
array1.concat(array2, array3, ..., arrayN)
```

- **array1**: El array base al que se agregarán otros elementos o arrays.
- **array2, ..., arrayN**: Los elementos o arrays que se quieren concatenar a `array1`.

#### **Características**

- Puede concatenar múltiples arrays en una sola llamada.
- También permite agregar valores individuales, no solo arrays.

#### **Ejemplo básico**

```javascript
const frutas = ["manzana", "pera"];
const verduras = ["lechuga", "zanahoria"];
const bebidas = ["agua", "jugo"];

const supermercado = frutas.concat(verduras, bebidas);

console.log(supermercado);
// Salida: ['manzana', 'pera', 'lechuga', 'zanahoria', 'agua', 'jugo']
```

#### **Ejemplo con valores individuales**

```javascript
const numeros = [1, 2, 3];
const concatenado = numeros.concat(4, 5, [6, 7]);

console.log(concatenado);
// Salida: [1, 2, 3, 4, 5, 6, 7]
```

### **Notas importantes**

1. Si un elemento que se pasa a `concat()` es un array, sus elementos se agregan al nuevo array, no el array en sí.
2. Los arrays originales no se modifican, manteniendo su estado inicial.

[Volver al índice](#índice)
