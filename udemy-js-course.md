# The complete javascript course UDEMY

## Índice

- [Basic operators](#basic-operators)
- [Falsy and truthy](#falsy-and-truthy)
- [Switch statement](#switch-statement)
- [Expresions and declaractions](#expresiones-y-declaraciones-en-javascript)
- [Ternary operator](#operador-condicional-o-ternario-en-javascript)

## Basic operators

```
//Math operators
      const now = 2037;
      const ageTuna = now - 1981;
      const ageToty = now - 1975;
      console.log(ageTuna, ageToty);

      console.log(ageTuna * 2, ageToty / 10, 2 ** 3);
      // 2 ** 3 means 2 to the power of 3 = 2 * 2 * 2

      const firstName = "Trakula";
      const lastName = "Tulachi";
      console.log(firstName + "" + lastName);

      //Assignment operators
      let x = 10 + 5;
      x += 10; // x = X + 10 = 25
      x *= 4; // x = x * 4 = 100
      x++; // x = x + 1
      x--; // x = x -1
      console.log(x);

      //Comparison operators
      console.log(ageToty > ageTuna);
      console.log(ageTuna >= 18);

      const isFullAge = ageTuna >= 18;

      console.log(now - 1975 > now - 1981);
`
``
```

## Falsy and truthy

En JavaScript, los valores **falsy** son aquellos que se consideran "falsos" cuando se evalúan en un contexto booleano (por ejemplo, en una declaración `if`). Los valores **truthy**, por el contrario, son considerados "verdaderos". Aquí te dejo algunos ejemplos:

### Falsy:

Estos son los valores que se evalúan como `false`:

- `false`
- `0`
- `""` (cadena vacía)
- `null`
- `undefined`
- `NaN`

### Truthy:

Cualquier valor que no sea **falsy** es **truthy**, es decir, se evalúa como `true`. Algunos ejemplos:

- `1`
- `"texto"`
- `[]` (array vacío)
- `{}` (objeto vacío)
- `Infinity`
- cualquier valor distinto de los mencionados en la lista de falsy

En resumen, **falsy** son los valores que se consideran falsos en un contexto booleano, y **truthy** son los que se consideran verdaderos.

## Switch statement

Es una forma alternativa de escribir logica condicional if else, cuando tienes un value que quieres comparar multiples elementos.

Un **`switch` statement** en JavaScript es una estructura de control que evalúa una expresión y ejecuta el bloque de código correspondiente al primer caso coincidente. Es útil cuando tienes múltiples condiciones que evaluar y deseas una forma más clara y legible que usar múltiples `if-else`.

### Sintaxis básica:

```javascript
switch (expresión) {
  case valor1:
    // Bloque de código para valor1
    break;
  case valor2:
    // Bloque de código para valor2
    break;
  default:
  // Bloque de código si no coincide ningún caso
}
```

- **`expresión`**: Es evaluada una vez y su valor se compara con los valores en los `case`.
- **`case`**: Representa un posible valor de la expresión.
- **`break`**: Termina la ejecución del `switch` para evitar que continúe con otros casos.
- **`default`**: Es opcional y se ejecuta si ningún caso coincide.

### Ejemplo de `switch`:

```javascript
const day = 3;

switch (day) {
  case 1:
    console.log("Lunes");
    break;
  case 2:
    console.log("Martes");
    break;
  case 3:
    console.log("Miércoles");
    break;
  default:
    console.log("Día no válido");
}
```

**Salida**: `Miércoles`

### Comparación con `if-else`:

El mismo ejemplo usando `if-else`:

```javascript
if (day === 1) {
  console.log("Lunes");
} else if (day === 2) {
  console.log("Martes");
} else if (day === 3) {
  console.log("Miércoles");
} else {
  console.log("Día no válido");
}
```

### Diferencias clave:

| **Aspecto**         | **`switch`**                                                       | **`if-else`**                                                        |
| ------------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------- |
| **Legibilidad**     | Más claro para múltiples condiciones basadas en valores concretos. | Puede volverse difícil de leer con muchas condiciones.               |
| **Rendimiento**     | Potencialmente más rápido si hay muchos casos.                     | Evalúa cada condición una por una.                                   |
| **Flexibilidad**    | Limitado a igualdad estricta (`===`).                              | Puede usar cualquier condición lógica (comparaciones, rangos, etc.). |
| **Uso recomendado** | Cuando tienes un conjunto fijo de valores para evaluar.            | Para condiciones más complejas o dinámicas.                          |

### Cuándo usar cuál:

- Usa `switch` cuando evalúas un solo valor contra múltiples casos específicos.
- Usa `if-else` cuando necesitas evaluar rangos, combinaciones de condiciones o lógica más compleja.

## Expresiones y Declaraciones en JavaScript

### **Expresión**

Una **expresión** es cualquier fragmento de código que se evalúa para producir un valor. Esto incluye desde valores simples hasta operaciones más complejas.

### **Ejemplos de expresiones:**

```javascript
42; // Una expresión literal que evalúa a 42
a + b; // Una expresión que suma los valores de 'a' y 'b'
Math.max(10, 20); // Una expresión que evalúa el mayor valor entre 10 y 20
true && false; // Una expresión lógica que evalúa a false
```

Las expresiones pueden ser usadas en cualquier lugar donde se espere un valor, como argumentos de funciones, asignaciones o condiciones.

### Declaración

Una declaración es un conjunto de instrucciones que realiza una acción o define algo, como variables, funciones o estructuras de control. Las declaraciones no producen un valor directamente (aunque algunas pueden contener expresiones).

Ejemplos de declaraciones:

```javascript
let x = 10; // Declaración de variable
function greet() {
  // Declaración de función
  console.log("Hola!");
}

if (x > 5) {
  // Declaración condicional
  console.log("x es mayor que 5");
}
```

### Diferencia clave

Expresión: Produce un valor. Ejemplo: 2 + 2, Math.random().
Declaración: Realiza una acción o define algo. Ejemplo:

`let a = 10, if (true) { ... }.`

## Operador Condicional (o Ternario) en JavaScript

### **Definición**

El **operador condicional** (también conocido como operador ternario) es una forma concisa de escribir una instrucción `if...else`. Este operador evalúa una condición y devuelve uno de dos valores dependiendo de si la condición es verdadera (`true`) o falsa (`false`).

### **Sintaxis**

```javascript
condición ? valorSiVerdadero : valorSiFalso;
```

1. **`condición`**: Una expresión que se evalúa como `true` o `false`.
2. **`valorSiVerdadero`**: El valor que se devuelve si la condición es `true`.
3. **`valorSiFalso`**: El valor que se devuelve si la condición es `false`.

### **Ejemplo práctico**

```javascript
const edad = 18;

// Usando operador ternario para verificar si es mayor de edad
const mensaje = edad >= 18 ? "Eres mayor de edad" : "Eres menor de edad";

console.log(mensaje); // Salida: "Eres mayor de edad"
```

### **Equivalente con `if...else`**

El ejemplo anterior escrito con `if...else` sería:

```javascript
let mensaje;

if (edad >= 18) {
  mensaje = "Eres mayor de edad";
} else {
  mensaje = "Eres menor de edad";
}

console.log(mensaje); // Salida: "Eres mayor de edad"
```

### **Ventajas del operador ternario**

- **Compacto**: Reduce la cantidad de líneas de código.
- Ideal para **asignaciones rápidas** o decisiones simples.

### **Nota importante**

Si la lógica es compleja o requiere múltiples condiciones, es preferible usar `if...else` para mantener la claridad del código.

---

notas ejercicio codificacion operador ternario

- crear un programa que calcule la propina de acuerdo a una cuenta
- crear variables cuenta, propina y total
- crear condicional ternario para calculo: condicion si cuenta es mayor a igual a 50 y menor o igual a 300, la propina sera 15% de la cuenta. De lo contrario será 20%
  - imprimir por consola la cuenta, la propina y el total
