# Clase 05 Array methods

# Índice

- [Qué son los métods de arrays](#qué-son-los-métodos-de-arrays)
- [Push, Unshift, Splice](#push-unshift-y-splice-en-javascript)
- [Shift, Splice, Pop](#shift-splice-pop-eliminar-elementos-de-un-array-en-javascript)
- [Includes](#método-includes)
- [Lenght](#lenght)

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
