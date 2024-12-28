# Índice temático GitHub

- [1. Flujo de trabajo estándar](#flujo-de-trabajo-estándar)
- [2. Check repo local con remoto](#2-check-repo-local-con-remoto)
- [10. Introducción a la Gestión de Repositorios](#1-introducción-a-la-gestión-de-repositorios)
- [2. Manejo de Cambios y Conflictos](#2-manejo-de-cambios-y-conflictos)
- [3. Organización de Archivos y Nomenclatura](#3-organización-de-archivos-y-nomenclatura)
- [4. Submódulos y Problemas Relacionados](#4-submódulos-y-problemas-relacionados)
- [5. Solución de Problemas Frecuentes](#5-solución-de-problemas-frecuentes)
- [6. Comandos Avanzados y Prácticas Óptimas](#6-comandos-avanzados-y-prácticas-óptimas)
- [7. Buenas Prácticas para Documentación](#7-buenas-prácticas-para-documentación)
- [8. Estrategia de Respaldo y Sincronización](#8-estrategia-de-respaldo-y-sincronización)

---

## 1. Flujo de trabajo estándar

En Git, el flujo de trabajo estándar es **hacer un `add`**, luego un **`commit`**, y finalmente un **`push`**. Este es el proceso típico para asegurarte de que los cambios que realizas estén correctamente registrados en tu repositorio local antes de enviarlos al repositorio remoto. Aquí te explico cada paso:

1. **`git add .`**: Este comando agrega todos los archivos modificados al área de preparación (staging area) para el siguiente commit. Puedes especificar archivos específicos en lugar de usar el punto (.) si no quieres agregar todos los cambios.
2. **`git commit -m "mensaje"`**: El commit guarda los cambios en tu repositorio local con un mensaje que describe lo que has hecho. Es importante que el mensaje sea claro y conciso.

3. **`git push`**: Finalmente, este comando sube los commits locales al repositorio remoto.

Sin embargo, si ya tienes los cambios preparados y deseas hacer todo en un solo paso, puedes usar:

- **`git commit -am "mensaje"`**: Esto es una forma abreviada de agregar y hacer commit de los archivos que ya están siendo rastreados por Git (es decir, no nuevos archivos no rastreados). Sin embargo, si has creado nuevos archivos, deberás agregar esos archivos con `git add` antes de hacer commit.

En resumen, **no puedes hacer un `push` directamente sin hacer antes un `add` y un `commit`** si los cambios son nuevos o modificados, ya que Git necesita tener esos cambios registrados localmente antes de enviarlos al repositorio remoto.

Aquí tienes los comandos para verificar si tu repositorio local está vinculado a uno remoto y, si no lo está, vincularlo:

## 2. Check repo local con remoto

Usa el siguiente comando para listar las URL de los repositorios remotos asociados:

```bash
git remote -v
```

- Si el repositorio está vinculado, verás algo como esto:

  ```
  origin  https://github.com/usuario/nombre-repo.git (fetch)
  origin  https://github.com/usuario/nombre-repo.git (push)
  ```

- Si no aparece nada, significa que tu repositorio local no está vinculado a un remoto.

### **Vincular tu repositorio local a un remoto**

Si no está vinculado, puedes asociarlo a un repositorio remoto usando el comando:

```bash
git remote add origin https://github.com/usuario/nombre-repo.git
```

- **`origin`** es el nombre del remoto. Es una convención común usar "origin", pero puedes elegir otro nombre si lo prefieres.
- **`https://github.com/usuario/nombre-repo.git`** es la URL del repositorio remoto que deseas vincular.

### **Verificar que el vínculo fue exitoso**

Ejecuta nuevamente:

```bash
git remote -v
```

Deberías ver la URL del remoto para `fetch` y `push`.

### **Hacer un push inicial (si es necesario)**

Si acabas de vincular tu repositorio local y el remoto está vacío, necesitarás hacer un push inicial:

```bash
git branch -M main
git push -u origin main
```

Esto asegura que la rama `main` (o la que estés usando) esté configurada como la rama por defecto vinculada al remoto.

## 1. Introducción a la Gestión de Repositorios

Cuando clonas un repositorio desde GitHub a tu máquina local, este queda vinculado automáticamente al repositorio remoto. Si no ocurre, puedes verificar la vinculación con:

```bash
git remote -v
```

Si necesitas vincularlo manualmente, usa:

```bash
git remote add origin <URL-del-repositorio>
```

## 2. Manejo de Cambios y Conflictos

Al trabajar con Git, es importante entender cómo manejar cambios locales y remotos. Usa:

- `git add` para preparar cambios.
- `git commit` para guardarlos localmente.
- `git push` para enviarlos al remoto.

Si encuentras conflictos al hacer `push`, primero integra los cambios remotos con:

```bash
git pull --rebase
```

## 3. Organización de Archivos y Nomenclatura

Usa una nomenclatura clara para mantener el orden. Por ejemplo:

- Para proyectos generales: `my-dev-path`.
- Para lecciones específicas: `bootcamp-mod-js-clase-04-arrays`.
- Para archivos independientes: `glosario`, `bd-css`.
  Evita subcarpetas si trabajas en diferentes máquinas para reducir problemas.

## 4. Submódulos y Problemas Relacionados

Los submódulos pueden causar conflictos si no se gestionan correctamente. Para simplificar, evita su uso y organiza todo en un solo repositorio.

## 5. Solución de Problemas Frecuentes

### Error: “Changes not staged for commit”

Solución:

1. Identifica los cambios pendientes con `git status`.
2. Agrégalos al área de preparación con:
   ```bash
   git add <archivo>
   ```

### Error: “Updates were rejected”

Si el remoto tiene cambios no presentes localmente, integra primero con:

```bash
git pull --rebase
```

Si no necesitas preservar los cambios remotos, fuerza el `push` con:

```bash
git push --force
```

## 6. Comandos Avanzados y Prácticas Óptimas

Ejecuta varios comandos en una línea usando `&&`:

```bash
git branch -M main && git remote add origin <URL> && git push -u origin main
```

## 7. Buenas Prácticas para Documentación

Mantén un archivo `README.md` para explicar la estructura y el propósito del repositorio. Documenta tus aprendizajes y prácticas en Markdown.

## 8. Estrategia de Respaldo y Sincronización

Para trabajar en múltiples dispositivos:

1. Asegúrate de sincronizar cambios regularmente.
2. Usa GitHub como repositorio central.
3. Al clonar en una nueva máquina, configura el remoto adecuadamente y verifica la rama principal.

---

### Resumen Final

La organización y gestión eficiente de repositorios GitHub, junto con una nomenclatura clara y buenas prácticas, facilita el manejo de archivos de estudio en Markdown. Este enfoque minimiza problemas y asegura un flujo de trabajo más fluido y estructurado.
