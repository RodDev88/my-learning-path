# The complete javascript course UDEMY

## Índice

- [Basic operators](#basic-operators)
- [Falsy and truthy](#falsy-and-truthy)
- [Switch statement](#switch-statement)

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
