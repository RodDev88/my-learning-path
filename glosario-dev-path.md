# GLOSARIO

## Índice

[- Lenguaje interpretado vs lenguaje compilado](#lenguaje-interpretado-vs-lenguaje-compilado)
[- Stack trace](#stack-trace)

## Lenguaje interpretado vs lenguaje compilado

Diferencia entre lenguaje interpretado y lenguaje compilado

    Un lenguaje interpretado ejecuta el código línea por línea a través de un intérprete en tiempo real, lo que permite una mayor flexibilidad pero generalmente hace que la ejecución sea más lenta. Un lenguaje compilado, en cambio, convierte el código completo en un archivo ejecutable mediante un compilador antes de su ejecución, lo que suele mejorar el rendimiento pero requiere recompilar cada vez que se hacen cambios.

    Ejemplo lenguaje interpretado: JS

        JavaScript es un ejemplo de un lenguaje interpretado, ya que su código se ejecuta en un entorno que lo interpreta, como el navegador o Node.js, donde es procesado línea por línea en tiempo de ejecución.

    Ejemplo lenguaje compilado: C++

        C++, por otro lado, es un lenguaje compilado. El código C++ debe ser compilado por un compilador (como GCC o Clang) antes de poder ejecutarse, lo que convierte el código fuente en un archivo binario ejecutable que la máquina puede correr directamente.

---

Lógica de negocios

    La lógica de negocios es el conjunto de reglas y procesos que definen cómo opera una aplicación o sistema para cumplir los objetivos específicos de una organización o negocio. Incluye la toma de decisiones, el procesamiento de datos y las operaciones que traducen los requisitos de negocio en funciones que la aplicación ejecuta, separando las reglas del negocio de otros aspectos técnicos de la aplicación.

---

Runtime JS:

    Un runtime de JavaScript es el entorno donde se ejecuta el código JavaScript. Este entorno contiene elementos clave como el motor de ejecución (por ejemplo, V8 en Chrome) y APIs que permiten al código interactuar con el sistema (por ejemplo, para acceder a la red o al sistema de archivos). Los runtimes, como Node.js para entornos de servidor, extienden las capacidades de JavaScript más allá del navegador.

---

Generado dinámicamente

    ¿Qué significa "generado dinámicamente"?
    Cuando se dice que algo es "generado dinámicamente", se refiere a que el contenido o los elementos de la página no están predefinidos en el HTML, sino que se crean o modifican en tiempo real a través de código JavaScript.

    Explicación sencilla:
    Generar dinámicamente significa que el contenido no está en el HTML desde el principio. En lugar de tener una lista fija de elementos, como:

```javascript
<ul>
  <li>Javiera</li>
  <li>Camila</li>
</ul>
```

    Se crea el contenido de la lista después de que la página ha cargado, a través de código. El script de JavaScript genera la lista en el momento en que se ejecuta el código, por ejemplo, al cargar la página o como resultado de una acción del usuario.

    En tu ejemplo:

```javascript
const data = ["Javiera", "Camila", "Francisco"];
for (let item of data) {
  d.innerHTML += `<li> ${item} </li>`;
}
```

    Aquí, los elementos <li> se agregan al <ul> después de que la página ha sido cargada. El contenido no estaba en el HTML original, sino que se creó dinámicamente a través de JavaScript.

    ¿Por qué es importante?
    Flexibilidad: Puedes cambiar o actualizar el contenido de la página sin tener que recargarla.
    Interactividad: El contenido puede adaptarse según las acciones del usuario (como hacer clic, enviar un formulario, etc.).

## Stack trace

El registro o mensaje que imprime la terminal cuando ocurre un error generalmente se llama **"stack trace"** o **"traceback**, dependiendo del contexto y el lenguaje de programación que estés utilizando.

---

### **1. Stack Trace**

- Es una lista detallada de llamadas a funciones y líneas de código que llevaron al error.
- Aparece principalmente en lenguajes como JavaScript, Java, o C#.
- Permite rastrear el origen del problema en el código.

Por ejemplo, en JavaScript:

```plaintext
TypeError: Cannot read property 'foo' of undefined
    at someFunction (script.js:10:5)
    at main (script.js:20:3)
```

---

### **2. Traceback**

- Es el término común en Python y otros lenguajes similares.
- Similar al stack trace, muestra una lista de errores y la secuencia de llamadas que llevaron a ellos.

Ejemplo en Python:

```plaintext
Traceback (most recent call last):
  File "script.py", line 5, in <module>
    some_function()
  File "script.py", line 3, in some_function
    1 / 0
ZeroDivisionError: division by zero
```

---

### **Otros términos comunes**

- **Error log (registro de errores):** Usado para describir cualquier mensaje de error, no necesariamente un stack trace.
- **Output (salida):** En un contexto más general, cualquier información que imprime la terminal, incluyendo errores.
- **Debugging output:** Mensajes impresos intencionalmente por el desarrollador para rastrear el estado del programa.

---

Si necesitas ayuda para interpretar un stack trace o resolver un error específico, ¡puedes compartirlo y lo revisamos juntos! 😊
