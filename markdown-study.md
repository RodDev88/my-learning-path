# Bienvenido a Markdown

Markdown es **fácil de usar** y muy _flexible_.

- Es legible en crudo
- Se convierte fácilmente a HTML
- Ideal para notas o documentación

---

## Definición

Markdown no es un lenguaje de programación, sino un lenguaje de marcado. Este tipo de lenguaje se utiliza para dar formato al texto de manera sencilla y legible tanto en su forma cruda (sin procesar) como en su versión renderizada (convertida, por ejemplo, a HTML).

Es más comparable a lenguajes como HTML que a lenguajes de programación como JavaScript o Python.

Características principales de Markdown:

Simplicidad: Usa caracteres comunes para definir títulos, listas, negritas, enlaces, etc.

Legibilidad: El texto sin procesar sigue siendo fácil de leer.
Portabilidad: Markdown se puede convertir a HTML u otros
formatos para su uso en sitios web, documentos y más.

## 1. Títulos y subtítulos

Usa los símbolos # para crear títulos. Cuantos más #, más pequeño será el título.

# Título principal

## Subtítulo nivel 1

### Subtítulo nivel 2

#### Subtítulo nivel 3

---

## 2. Listas

Listas con viñetas:
Usa -, \* o + para crear una lista desordenada.

- Elemento 1
  - Sub-elemento 1.1
  - Sub-elemento 1.2
- Elemento 2

Listas numeradas:
Usa números seguidos de un punto.

1. Elemento 1

2. Elemento 2
   1. Sub-elemento 2.1
   2. Sub-elemento 2.2

## 3. Texto destacado

Cursiva:
Coloca el texto entre asteriscos o guiones bajos.

_Texto en cursiva_  
_Texto en cursiva_

Negrita:
Coloca el texto entre dobles asteriscos o dobles guiones bajos.

**Texto en negrita**  
**Texto en negrita** (vs code automaticamente los tr en \* )

Cursiva y negrita:
Combina tres asteriscos o guiones bajos.

**_Texto en cursiva y negrita_**  
**_Texto en cursiva y negrita_**

## 4. Código

Código en línea:
Coloca el código entre comillas invertidas (backticks):

`console.log("Hola Mundo");`

Bloque de código:
Usa tres comillas invertidas y especifica el lenguaje:

```javascript
function saludo() {
  console.log("Hola Mundo");
}
```

## 5. Bloques de cita

Usa el símbolo > para citas.

> Esto es una cita.
>
> > Las citas pueden anidarse.

## 6. Enlaces y otros estilos

Enlace

[Texto del enlace](https://ejemplo.com)

Imagen

![Texto alternativo](https://placedog.net/200)

## 7. Línea de separacion

En Markdown, puedes usar una línea horizontal como separador de contenido con tres o más guiones (---), asteriscos (\*\*\*) o guiones bajos (\_\_\_) seguidos. No debe haber texto en la misma línea. Aquí tienes cómo hacerlo:

Texto anterior al separador.

---

Texto posterior al separador.
