# MODULO 3 JAVASCRIPT

## Clase 04 Arrays

# Conceptos básicos de arreglos en JavaScript

Un **arreglo** (o array) en JavaScript es una estructura de datos que permite almacenar una colección ordenada de elementos. Estos elementos pueden ser de cualquier tipo: números, cadenas, objetos, otros arreglos, etc.

## Conceptos básicos sobre arreglos

1. **Índices**:  
   Los elementos de un arreglo están ordenados y cada uno tiene un índice, que comienza desde `0`. Por ejemplo, el primer elemento tiene índice `0`, el segundo índice `1`, y así sucesivamente.

2. **Creación de un arreglo**:  
   Puedes crear un arreglo utilizando:

   - Corchetes `[]`.
   - La palabra clave `new Array()` (aunque esta última no se usa comúnmente).

3. **Métodos y propiedades**:  
   Los arreglos tienen métodos y propiedades que permiten manipularlos. Por ejemplo:
   - `.length`: Devuelve la cantidad de elementos en el arreglo.
   - `.push()`: Agrega un elemento al final del arreglo.
   - `.pop()`: Elimina el último elemento del arreglo.
   - `.shift()`: Elimina el primer elemento.
   - `.unshift()`: Agrega un elemento al inicio.
   - `.forEach()`, `.map()`, `.filter()`, etc., son métodos avanzados para recorrer o transformar arreglos.

## Ejemplo básico de un arreglo

```javascript
// Crear un arreglo con algunos elementos
const frutas = ["manzana", "banana", "cereza"];

// Acceder a elementos del arreglo
console.log(frutas[0]); // "manzana"
console.log(frutas[1]); // "banana"

// Modificar un elemento del arreglo
frutas[1] = "naranja";
console.log(frutas); // ["manzana", "naranja", "cereza"]

// Agregar un nuevo elemento
frutas.push("uva");
console.log(frutas); // ["manzana", "naranja", "cereza", "uva"]

// Eliminar el último elemento
frutas.pop();
console.log(frutas); // ["manzana", "naranja", "cereza"]

// Saber cuántos elementos tiene el arreglo
console.log(frutas.length); // 3
```

## ¿Qué es un ciclo `for`?

Un **ciclo `for`** en JavaScript es una estructura de control que permite repetir un bloque de código un número determinado de veces. Es muy útil para recorrer arreglos, realizar cálculos repetitivos o ejecutar cualquier tarea en la que se necesite iteración.

### Estructura básica de un ciclo `for`

```javascript
for (inicialización; condición; actualización) {
  // Bloque de código que se ejecuta en cada iteración
}
```

**_Inicialización:_** Se ejecuta una vez al inicio del ciclo. Generalmente, se utiliza para declarar e inicializar una variable de control (como i).

**_Condición:_** Se evalúa antes de cada iteración. Si es true, el bloque de código dentro del ciclo se ejecuta. Si es false, el ciclo termina.

**_Actualización:_** Se ejecuta al final de cada iteración y, normalmente, se utiliza para modificar la variable de control.

### Ejemplo ciclo `for`

```javascript
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
//salida en consola
1;
2;
3;
4;
5;
```

### Explicación del ejemplo

Inicialización: let i = 1
Se declara la variable i y se le asigna el valor inicial de 1.

Condición: i <= 5
El ciclo continuará ejecutándose mientras i sea menor o igual a 5.

Bloque de código: console.log(i)
En cada iteración, se imprime el valor actual de i.

Actualización: i++
Después de cada iteración, el valor de i aumenta en 1.

### Recorrer un arreglo con un ciclo `for`

Los ciclos for son especialmente útiles para trabajar con arreglos. Aquí tienes un ejemplo práctico:

```javascript
const colores = ["rojo", "verde", "azul", "amarillo"];

for (let i = 0; i < colores.length; i++) {
  console.log(`Color en posición ${i}: ${colores[i]}`);
}
//salida en consola
Color en posición 0: rojo
Color en posición 1: verde
Color en posición 2: azul
Color en posición 3: amarillo

```

### Explicación del ejemplo con arreglo

Inicialización: let i = 0
Comenzamos desde el primer índice del arreglo (0).

Condición: i < colores.length
El ciclo se ejecuta mientras i sea menor que la longitud del arreglo.

Bloque de código:
Se utiliza colores[i] para acceder al elemento actual del arreglo.

Actualización: i++
Incrementamos i en 1 después de cada iteración.

### Revisión de línea de código

```javascript
console.log(`Color en posición ${i}: ${colores[i]}`);
```

1.  Uso de Template Literals (Plantillas de cadena)
    En lugar de usar comillas simples ' ' o comillas dobles " ", se están usando backticks (acento grave: `). Esto se conoce como Template Literals en JavaScript.

        - Los Template Literals permiten:

            Incluir variables y expresiones dentro de una cadena usando ${}.

            Escribir cadenas de texto en varias líneas sin necesidad de concatenar.

---

2. La expresión ${i}

   - i es la variable de control del ciclo for que va cambiando en cada iteración.
   - Al colocar ${i} dentro del Template Literal, JavaScript reemplaza esa expresión con el valor actual de i.

     - Ejemplo:

     Si i = 0, entonces ${i} será reemplazado por 0.

---

3. La expresión ${colores[i]}

- Colores es un arreglo que contiene varios elementos, como "rojo", "verde", etc.
- colores[i] accede al elemento del arreglo en la posición i.
  Ejemplo:

        Si i = 0, entonces colores[i] será colores[0], que es "rojo".

        Si i = 1, entonces colores[i] será colores[1], que es "verde".

---

4. El resultado final

- Al combinar todo en el Template Literal, JavaScript reemplaza las expresiones ${i} y ${colores[i]} con sus respectivos valores.

- Por ejemplo, si el arreglo colores es:

```javascript
const colores = ["rojo", "verde", "azul", "amarillo"];
```

Durante cada iteración del ciclo for:

**_Primera iteración (i = 0):_**

```javascript
console.log(`Color en posición ${i}: ${colores[i]}`);
```

Color en posición 0: rojo;

**_Segunda iteración (i = 1):_**

Color en posición 1: verde;

y así sucesivamente...

**_El console.log combina texto fijo con valores dinámicos usando Template Literals.
La sintaxis ${} permite insertar variables o expresiones dentro de una cadena sin necesidad de concatenar manualmente._**

---

# Estructuras de control, iteración y variable de control en JavaScript

## 1. ¿Qué son las estructuras de control en JavaScript?

Las **estructuras de control** son bloques de código que permiten tomar decisiones o repetir acciones en función de ciertas condiciones. Se dividen principalmente en dos tipos:

### a) **Estructuras condicionales**

Permiten ejecutar un bloque de código solo si se cumple una condición.

- **`if`, `else if`, `else`**:

  ```javascript
  const edad = 18;

  if (edad >= 18) {
    console.log("Eres mayor de edad.");
  } else {
    console.log("Eres menor de edad.");
  }
  ```

- **`switch`** (para múltiples casos):

  ```javascript
  const dia = "lunes";

  switch (dia) {
    case "lunes":
      console.log("Inicio de semana.");
      break;
    case "viernes":
      console.log("Fin de semana cerca.");
      break;
    default:
      console.log("Día común.");
  }
  ```

---

### b) **Estructuras de bucle o repetición**

Permiten ejecutar un bloque de código varias veces (iteraciones).

- **`for`**: Itera un número específico de veces.

  ```javascript
  for (let i = 0; i < 5; i++) {
    console.log(i);
  }
  ```

- **`while`**: Se ejecuta mientras la condición sea verdadera.

  ```javascript
  let i = 0;
  while (i < 5) {
    console.log(i);
    i++;
  }
  ```

- **`do...while`**: Ejecuta al menos una vez, luego verifica la condición.

  ```javascript
  let i = 0;
  do {
    console.log(i);
    i++;
  } while (i < 5);
  ```

- **`for...of`**: Recorre elementos de un arreglo o iterable.

  ```javascript
  const colores = ["rojo", "verde", "azul"];
  for (const color of colores) {
    console.log(color);
  }
  ```

- **`for...in`**: Recorre las propiedades de un objeto.
  ```javascript
  const persona = { nombre: "Ana", edad: 25 };
  for (const clave in persona) {
    console.log(`${clave}: ${persona[clave]}`);
  }
  ```

---

## 2. ¿Qué es una iteración?

Una **iteración** es cada **repetición** que ocurre dentro de un bucle. Es decir, cuando el bloque de código dentro de una estructura de repetición se ejecuta, decimos que ha ocurrido una iteración.

### Ejemplo de iteraciones con un ciclo `for`:

```javascript
for (let i = 1; i <= 3; i++) {
  console.log(`Iteración número: ${i}`);
}
//salida de consola

Iteración número: 1
Iteración número: 2
Iteración número: 3

```

Aquí el ciclo realiza 3 iteraciones, porque el bloque de código se ejecuta 3 veces.

---

## 3. ¿Qué es la variable de control en un ciclo for?

La variable de control es una variable que controla cuántas veces se ejecutará un ciclo. Generalmente se declara en la inicialización del ciclo for.

Ejemplo:

```javascript
Copiar código
for (let i = 0; i < 3; i++) {
    console.log(i);
}
```

### Desglose del ciclo:

let i = 0: Aquí se inicializa la variable de control i con el valor 0.

i < 3: Esta es la condición. Mientras i sea menor que 3, el ciclo se ejecutará.

i++: Esto actualiza la variable de control, incrementando su valor en 1 después de cada iteración.

---

## Diferencia entre el ciclo for...of y el ciclo for tradicional

Ciclo for tradicional

El ciclo for tradicional en JavaScript tiene esta estructura:

```javascript
for (inicialización; condición; actualización) {
  // Código que se ejecuta en cada iteración
}
//Ejemplo de un ciclo for tradicional:

for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

Ciclo for...of

Es una forma más sencilla de recorrer los elementos de un arreglo o cualquier otro objeto iterable (como cadenas, mapas, conjuntos, etc.). La estructura es:

```javascript
for (let item of arreglo) {
  // Código que se ejecuta con cada elemento del arreglo
}

//ejemplo ciclo for ..of
const data = ["Javiera", "Camila", "Francisco"];
for (let item of data) {
  console.log(item);
}
```

- No necesitas inicializar una variable de índice ni comprobar una condición. El ciclo recorre directamente cada elemento del arreglo data.
- El ciclo se detiene automáticamente cuando ya no quedan elementos.

**_Resumen_**

- for tradicional: Se define un índice, una condición y una actualización explícita en cada iteración.
- for...of: Se utiliza cuando solo quieres recorrer los elementos de un arreglo (o cualquier objeto iterable), sin preocuparte por el índice o las condiciones manualmente.

---

## Resumen conceptos: Array - Object - Arreglo de objetos

1. Arreglo (Array)

Un arreglo es una lista ordenada de valores que pueden ser de cualquier tipo (números, strings, objetos, etc.). Cada valor en un arreglo tiene una posición (índice) que comienza en 0.

```javascript
const frutas = ["manzana", "plátano", "uva", "kiwi"];

console.log(frutas[0]); // "manzana" (índice 0)
console.log(frutas[2]); // "uva" (índice 2)
frutas.push("naranja"); // Agrega un elemento al final
console.log(frutas); // ["manzana", "plátano", "uva", "kiwi", "naranja"]
```

Características clave:

- Es una colección ordenada.
- Accedes a los elementos mediante índices numéricos.
- Métodos comunes: push(), pop(), forEach(), map().

2. Objeto (Object)

   Un objeto es una estructura que almacena datos en pares clave-valor. Las claves son strings (o símbolos) y permiten acceder a los valores asociados.

Ejemplo de objeto:
javascript
Copiar código
const persona = {
nombre: "Rodrigo",
edad: 30,
profesion: "Desarrollador",
saludar: function() {
return `Hola, soy ${this.nombre} y tengo ${this.edad} años.`;
}
};

console.log(persona.nombre); // "Rodrigo"
console.log(persona["profesion"]); // "Desarrollador"
console.log(persona.saludar()); // "Hola, soy Rodrigo y tengo 30 años."
Características clave:
Almacena información estructurada mediante claves y valores.
Puedes acceder a los valores con la notación punto (objeto.propiedad) o corchetes (objeto["propiedad"]).
Métodos y funciones pueden estar dentro del objeto. 3. Arreglo de objetos
Un arreglo de objetos es una combinación de los dos anteriores: un arreglo que contiene varios objetos. Es útil cuando quieres manejar una lista de elementos con múltiples propiedades.

Ejemplo de arreglo de objetos:
javascript
Copiar código
const productos = [
{ id: 1, nombre: "Cafetera", precio: 23990, color: "rojo" },
{ id: 2, nombre: "Tostadora", precio: 15990, color: "blanco" },
{ id: 3, nombre: "Licuadora", precio: 29990, color: "negro" }
];

// Acceder al primer objeto
console.log(productos[0].nombre); // "Cafetera"

// Recorrer el arreglo de objetos
productos.forEach((producto) => {
console.log(`${producto.nombre} cuesta $${producto.precio} y es de color ${producto.color}`);
});

/_ Salida:
Cafetera cuesta $23990 y es de color rojo
Tostadora cuesta $15990 y es de color blanco
Licuadora cuesta $29990 y es de color negro
_/
Características clave:
Cada elemento del arreglo es un objeto.
Permite organizar múltiples objetos de manera ordenada.
Puedes usar métodos como forEach(), map() o filter() para recorrer y manipular el arreglo.

---

## Clase 03 Functions

## Ejercicio Funciones: Fx, parameters and return

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

Clase 1 JS Intro variables

---

INDEX CLASE del profe ( no la del pdf de Desafío Latam)con fines orientativos

1. Historia
   - 1995 > X
   - Netscape 2
   - Mozilla
   - BUM
   - Timeline
2. Variables
   - Tipos de variables
   - Tipos de datos
     - Primitivos
3. Runtime

   - Chromium (https://www.chromium.org/chromium-projects/)

   * Node.js (https://nodejs.org/en/)
   * Deno (https://deno.com/)

4. Condiciones
   - If
   - If, else-if, else
   - Operadores comparación

---

Clase 2 Javascript Condiciones

---

Esquema para enfrentar un ejercicio, así lo ordeno el profe Francisco y creo que es muy útil para sortear la confusa redacción del desafío Latam

1. Agregar los elementos al HTML (input, botón y párrafo o span)
   HTML
   - <input id/>
   - <button onclick="validarPassword()">
   - <p>
2. Agregar evento al disparador (el botón)
   onclick = "validarPassword()"
3. Seleccionar el valor del input y guardarlo en una variable
   utilizamos document.querySelector()
4. Si se cumple la condicion
   a. Seleccionar el párrafo
   b. Modificar el contenido del parrafo (.innerHTML) mostrando "Lo lograste"

FROM CHAPGPT

    Diferencia entre if, else-if y else:

    En JavaScript, if evalúa una condición y ejecuta el bloque de código asociado si esta es verdadera. else-if se usa después de un if para agregar una segunda condición si la primera no se cumple. else, en cambio, no tiene una condición; simplemente ejecuta el bloque asociado si ninguna de las condiciones anteriores fue verdadera.

    El if y el else en JavaScript se utilizan para evaluar condiciones en términos de "sí" o "no" (verdadero o falso):

    if ejecuta su bloque de código cuando la condición es verdadera.
    else actúa como una alternativa: si ninguna de las condiciones if o else-if anteriores es verdadera, entonces el bloque de else se ejecutará.

    De este modo, if y else forman una estructura básica de decisión binaria.

      LABEL E INPUTS

         Los elementos `<label>` son opcionales, y puedes trabajar directamente con los `<input>` si no necesitas etiquetas visuales para ellos.

         Sin embargo, los `<label>` tienen algunas ventajas en términos de accesibilidad y experiencia de usuario:

         ### **Ventajas de usar `<label>`:**

         1. **Accesibilidad:**

            - Asociar un `<label>` con un `<input>` permite que los lectores de pantalla describan el propósito del campo.
            - Puedes hacer esto usando el atributo `for` en el `<label>` y el `id` correspondiente en el `<input>`:
            ```html
            <label for="checkbox1">Opción 1</label>
            <input type="checkbox" id="checkbox1" />
            ```

         2. **Área clicable más grande:**

            - Cuando usas `<label>` asociado, puedes hacer clic tanto en el texto como en el checkbox.

         3. **Mejor legibilidad del código:**
            - Proporciona una descripción clara de qué representa cada `<input>`.

      OPERADOR TERNARIO

         El operador ternario es una forma compacta de escribir una instrucción condicional if-else. Tiene la siguiente sintaxis:

         condición ? valor_si_verdadero : valor_si_falso;

         Es decir, evalúa la condición y si es true ejecuta el primer valor (después del ?), si es false ejecuta el segundo valor (después de los :).



         ###
          Uso del Operador `||` para Asignación de Valores por Defecto

            El operador `||` no solo se utiliza para operaciones lógicas (como en comparaciones booleanas), sino también para **asignar un valor por defecto** a una variable.

            Esto es muy útil cuando queremos que una variable tenga un valor predeterminado en caso de que el valor ingresado por el usuario sea vacío, `null`, `undefined` o cualquier valor que se considere "falsy" en JavaScript.

                  ### **Concepto Básico**

                  El operador `||` evalúa la expresión de la izquierda (el valor que ha ingresado el usuario) y, si es un valor considerado "falsy", pasa a la expresión de la derecha (el valor por defecto). Si la primera expresión no es "falsy", entonces la variable toma ese valor.

                  ### **Valores "falsy" en JavaScript:**
                  En JavaScript, los siguientes valores se consideran "falsy":
                  - `false`
                  - `0`
                  - `""` (cadena vacía)
                  - `null`
                  - `undefined`
                  - `NaN`

                  ### **Sintaxis:**
                  ```javascript
                  variable = valor_ingresado || valor_por_defecto;
                  ```

                  Si `valor_ingresado` es "falsy", entonces se asigna `valor_por_defecto`.

                  ### **Ejemplo 1: Valor por Defecto con `""` (Cadena Vacía)**

                  Imagina que quieres que el usuario ingrese su nombre, pero si no lo hace, se le asigna un nombre predeterminado.

                  ```javascript
                  let nombre = "" || "Juan";  // El valor ingresado está vacío
                  console.log(nombre);  // "Juan"
                  ```

                  **Explicación:** El valor ingresado es una cadena vacía `""`, que es "falsy". Entonces, la variable `nombre` toma el valor por defecto `"Juan"`.

                  ### **Ejemplo 2: Valor por Defecto con `null`**

                  Supón que tenemos una variable que puede ser `null`, y queremos darle un valor por defecto si no se ha asignado ningún valor.

                  ```javascript
                  let edad = null || 25;  // El valor es null
                  console.log(edad);  // 25
                  ```

                  **Explicación:** El valor de `edad` es `null`, que es "falsy", por lo tanto, `edad` recibe el valor por defecto `25`.

                  ### **Ejemplo 3: Uso con un Valor Válido**

                  Si el usuario ingresa un valor válido, el operador `||` lo mantiene, y no se asigna el valor por defecto.

                  ```javascript
                  let nombre = "Carlos" || "Juan";  // El valor ingresado no está vacío
                  console.log(nombre);  // "Carlos"
                  ```

                  **Explicación:** El valor ingresado es `"Carlos"`, que es "truthy" (un valor válido), por lo que `nombre` conserva el valor `"Carlos"` y no se le asigna `"Juan"`.

                  ### **¿Por qué se usa esto?**

                  Es una forma rápida de asegurarte de que una variable siempre tenga un valor válido, incluso si el usuario no proporciona uno. Es una forma más concisa y limpia de escribir condiciones que, de otra manera, requerirían un bloque `if` más largo.

                  ### **Resumen:**

                  - El operador `||` selecciona el **primer valor "truthy"** entre dos expresiones.
                  - Si la primera expresión es "falsy", se toma el valor por defecto (segunda expresión).
                  - Es útil para asignar valores predeterminados de manera sencilla, sin tener que usar un bloque `if`.

                  ### **Alternativa con `if`:**
                  El mismo ejemplo con un `if` sería más largo:

                  ```javascript
                  let nombre;
                  if (nombre === "" || nombre === null || nombre === undefined) {
                     nombre = "Juan";
                  }
                  console.log(nombre);  // "Juan"
                  ```

                  Como ves, el operador `||` simplifica mucho ese proceso.


               ¡Con gusto! Los términos **"falsy"** y **"truthy"** se refieren a cómo JavaScript evalúa ciertos valores cuando se los utiliza en contextos booleanos, como en una condición `if`.


               FALSY && TRUTHY


               ### **¿Qué es un valor "truthy"?**

               Un **valor "truthy"** es cualquier valor que, cuando se evalúa en un contexto booleano (como dentro de un `if`), se considera como `true`. Es decir, cualquier valor que **no** sea "falsy".

               **Ejemplos de valores "truthy":**
               - Cualquier número que no sea 0 (como `1`, `-1`, `100`)
               - Cualquier cadena de texto que no sea vacía (como `"hola"`, `" "`, `"0"`)
               - Objetos (como `{}`, `[]`)
               - `true`
               - Funciones (como `function() {}`)

               #### **Ejemplo:**
               ```javascript
               let valor = "Hola";  // Cadena no vacía (truthy)
               if (valor) {
                  console.log("Es truthy");
               } else {
                  console.log("Es falsy");
               }
               // "Es truthy"
               ```

               En este caso, `"Hola"` es una cadena no vacía, por lo tanto es **truthy** y entra en el bloque `if`.

               ### **¿Qué es un valor "falsy"?**

               Un **valor "falsy"** es cualquier valor que, cuando se evalúa en un contexto booleano (como dentro de un `if`), se considera como `false`. Es decir, cualquier valor que sea **falsy** se tratará como `false` en una condición.

               **Valores "falsy" en JavaScript:**
               1. **`false`**: El valor booleano `false`.
               2. **`0`**: El número cero.
               3. **`""` (cadena vacía)**: Una cadena vacía.
               4. **`null`**: Un valor nulo.
               5. **`undefined`**: Una variable que no ha sido definida.
               6. **`NaN`**: "Not a Number" (un valor no numérico que resulta de operaciones inválidas).

               #### **Ejemplo:**
               ```javascript
               let valor = 0;  // El número 0 es falsy
               if (valor) {
                  console.log("Es truthy");
               } else {
                  console.log("Es falsy");
               }
               // "Es falsy"
               ```

               En este caso, `0` es un valor **falsy** y entra en el bloque `else`.

               ### **Resumen de valores "falsy" y "truthy"**

               #### **Valores "falsy":**
               - `false`
               - `0`
               - `""` (cadena vacía)
               - `null`
               - `undefined`
               - `NaN`

               #### **Valores "truthy"** (todos los demás valores):
               - Cualquier número distinto de `0` (como `1`, `-1`, `100`)
               - Cualquier cadena que no esté vacía (como `"texto"`)
               - Objetos y arrays (como `{}` y `[]`)
               - Funciones
               - `true`

               ### **¿Por qué es útil saberlo?**

               Conocer los valores "falsy" y "truthy" es muy útil para trabajar con condicionales y asignación de valores en JavaScript. Por ejemplo, cuando usas el operador `||` (OR lógico), como ya vimos, el operador selecciona el primer valor **truthy**. Esto permite escribir código más compacto y eficiente sin tener que hacer verificaciones explícitas.

               ### **Ejemplo con `||`:**
               ```javascript
               let nombre = "" || "Juan";
               console.log(nombre);  // "Juan"
               ```
               Aquí, `""` es **falsy**, por lo que se toma `"Juan"`, que es **truthy**.

---

Clase 3 Functions

---

-El profe partió compartiendo el sito roadmap.sh, especificamente el de frontend
https://roadmap.sh/full-stack

-Luego compartió el sitio Getonoboard y dio tips para elegir una postulación

-Mencionó los principios DRY, KISS (mantenlo simple, estupido), YAGNI (no hagas shit que no utilizaras)

-Definió las FX

-Definió los Parámetros como variables locales a la función, solo viven en ese bloque de código
-Pueden haber multiples parametros

-Definió el Hosting: orden interno de las variables en JS, el lenguje lleva arriba las declaraciones de las fx, al inicio del code

Clase

-Activación de conceptos

-Parametros por defecto: Iba como avión hasta el uso de parametros por defectos, donde recurrí a GPT para reforzar :)

         Los parámetros por defecto en JavaScript son valores que una función usa si no se proporcionan argumentos al llamarla. Aquí te dejo una explicación paso a paso con ejemplos para reforzar:

         Concepto Básico
         Cuando defines una función con parámetros por defecto, puedes asignar un valor inicial que se usará si el argumento correspondiente no se pasa.

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

---

SHORCUTS

---

Comentario bloque = shift + option + A

Backticks = `` = en Mac = cmd + ^(sombrerito)

Inpsector de elementos en Firefox = cmd + option + i

---

RECURSOS

---

Del curso de CSS Udemy

1. del profe https://codingheroes.io/resources/
2. HTML validator https://validator.w3.org/
3. Diffchecker https://www.diffchecker.com/ (para comparar códigos, p.e. el del profe y el mío)

---

GLOSARIO

---

Diferencia entre lenguaje interpretado y lenguaje compilado

    Un lenguaje interpretado ejecuta el código línea por línea a través de un intérprete en tiempo real, lo que permite una mayor flexibilidad pero generalmente hace que la ejecución sea más lenta. Un lenguaje compilado, en cambio, convierte el código completo en un archivo ejecutable mediante un compilador antes de su ejecución, lo que suele mejorar el rendimiento pero requiere recompilar cada vez que se hacen cambios.

    Ejemplo lenguaje interpretado: JS

        JavaScript es un ejemplo de un lenguaje interpretado, ya que su código se ejecuta en un entorno que lo interpreta, como el navegador o Node.js, donde es procesado línea por línea en tiempo de ejecución.

    Ejemplo lenguaje compilado: C++

        C++, por otro lado, es un lenguaje compilado. El código C++ debe ser compilado por un compilador (como GCC o Clang) antes de poder ejecutarse, lo que convierte el código fuente en un archivo binario ejecutable que la máquina puede correr directamente.

Lógica de negocios

    La lógica de negocios es el conjunto de reglas y procesos que definen cómo opera una aplicación o sistema para cumplir los objetivos específicos de una organización o negocio. Incluye la toma de decisiones, el procesamiento de datos y las operaciones que traducen los requisitos de negocio en funciones que la aplicación ejecuta, separando las reglas del negocio de otros aspectos técnicos de la aplicación.

Runtime JS:

    Un runtime de JavaScript es el entorno donde se ejecuta el código JavaScript. Este entorno contiene elementos clave como el motor de ejecución (por ejemplo, V8 en Chrome) y APIs que permiten al código interactuar con el sistema (por ejemplo, para acceder a la red o al sistema de archivos). Los runtimes, como Node.js para entornos de servidor, extienden las capacidades de JavaScript más allá del navegador.

# CSS DB

```body {
background-color: whitesmoke;
font-family: Arial, Helvetica, sans-serif;
margin: 0;
display: flex;
justify-content: center;
align-items: center;
height: 100vh;
}

.container {
width: 30%;
display: flex;
flex-direction: column;
align-items: center;
text-align: center;
padding: 20px;
background: white;
border-radius: 10px;
box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

input {
padding: 10px;
margin: 5px;
border-radius: 3px;
border: 1px solid #ccc;
width: 80%;
}

button {
background-color: black;
width: 50%;
color: white;
padding: 10px;
border-radius: 3px;
border: none;
cursor: pointer;
transition: background-color 0.3s, color 0.3s;
margin-top: 10px;
}

button:hover {
background-color: white;
color: black;
}

p {
font-size: large;
margin-top: 10px;
}
```
