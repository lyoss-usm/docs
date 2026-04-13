# Guía de Contribución (CONTRIBUTING.md)

¡Hola! 👋 Muchas gracias por tu interés en contribuir a este proyecto de la **Comunidad Linux y Open Source (Lyoss USM)**. 
Continuamente nos pica el bichito por codear algo y lo hacemos, siempre buscando generar un impacto real en la vida universitaria. No importa si estás en primer año, si es tu primera vez usando Git, o si ya eres un experto; **todas las contribuciones son bienvenidas**. 
Esta guía te explicará cómo trabajamos de forma general en nuestros proyectos para que tu experiencia sea fluida y educativa.

---

## 💬 ¿Necesitas ayuda o tienes dudas?

Entendemos que leer código nuevo puede ser intimidante. Si encuentras un Issue que quieres tomar pero no sabes por dónde empezar, o si te atascas en algún punto del desarrollo: **¡No te quedes en silencio!**

* Cada uno de nuestros proyectos tiene un canal público asignado.
* **Únete a nuestro servidor de Discord:** [**Ingresa aquí**](https://discord.gg/2mCzKu2yPV) y pregunta con toda confianza en el canal del proyecto. Los Jefes de Proyecto y Maintainers están ahí exactamente para guiarte.

---

## 🛠️ ¿Cómo empezar a programar?

Este documento explica la *metodología* general, pero las instrucciones técnicas específicas de cada proyecto viven en otro lado.

1. Para saber cómo descargar el código, instalar las dependencias y hacer correr el proyecto en tu computador, **por favor lee el archivo `README.md`** que se encuentra en la raíz de este repositorio.
2. Ve a la pestaña de **Issues** en GitHub.
3. Busca una tarea que te llame la atención y que esté libre. (💡 *Tip: Si eres nuevo, busca las etiquetas `good first issue` o `docs`*).
4. **Auto-asígnate** el Issue usando la opción "Assignees" o en la Sección Project. ¡No necesitas pedir permiso, la tarea es tuya!

---

## 🌿 Nuestro Flujo de Trabajo (Git)

Para evitar que el código se rompa, nunca trabajamos directamente sobre las ramas principales (`main` o `dev`).

1. Asegúrate de tener tu repositorio local actualizado.
2. Crea una rama nueva partiendo siempre desde la rama **`dev`**.
3. Nombra tu rama según lo que vayas a hacer:
   * `feature/nombre-de-tu-tarea` (Si es una funcionalidad nueva)
   * `fix/nombre-del-error` (Si vas a arreglar un bug)
   * `docs/nombre-del-documento` (Si solo vas a escribir o arreglar textos)

---

## ✍️ El Estándar de Commits (Conventional Commits)

En Lyoss USM queremos prepararte para la industria, por eso no aceptamos commits con mensajes como *"cambios"*, *"ahora si funciona"*, o *"asdfg"*. 
Utilizamos un estándar profesional llamado **Conventional Commits**. Es muy fácil de usar: cada commit debe empezar con una palabra clave que explique *qué tipo de cambio* hiciste.

### Tipos más comunes:
* **`feat:`** (Feature) Agregaste una nueva funcionalidad.
  * *Ejemplo:* `feat: agrega botón de modo oscuro`
* **`fix:`** Solucionaste un error o bug.
  * *Ejemplo:* `fix: corrige error al calcular el promedio`
* **`docs:`** Cambios únicamente en la documentación (como este archivo o el README).
  * *Ejemplo:* `docs: actualiza links de Discord`
* **`style:`** Cambios visuales o de formato de código que no afectan la lógica (espacios, punto y coma, etc).
* **`refactor:`** Cambios en el código que no arreglan un bug ni añaden una funcionalidad, pero mejoran la estructura interna.

Te recomendamos leer la [Documentación Oficial de Conventional Commits (en español)](https://www.conventionalcommits.org/es/v1.0.0/) para dominar esta habilidad.

---

## 🚀 Enviando tu código (Pull Requests)

¡Terminaste tu tarea! Ahora debes integrar tu código al proyecto:

1. Sube tu rama al repositorio en GitHub (`git push`).
2. Abre un **Pull Request (PR)**.
3. **MUY IMPORTANTE:** Tu PR siempre debe apuntar hacia la rama **`dev`**, nunca hacia `main`.
4. Rellena la plantilla que aparecerá automáticamente.
5. Para que nuestro tablero se mantenga ordenado, incluye en la descripción de tu PR una palabra clave seguida del número de tu Issue. 
   * *Ejemplo:* Escribe `Closes #12` o `Fixes #12` para que GitHub cierre ese Issue automáticamente cuando aprobemos tu código.
6. Espera la revisión de un Maintainer. Si te piden cambios, ¡no te desanimes! Es parte normal del proceso de aprendizaje. Haz los arreglos en tu misma rama y el PR se actualizará solo.

---

## 🏆 Reconocimiento a tu esfuerzo

El código abierto lo hacen las personas, y queremos celebrar tu trabajo. 

Al lograr que tu primer Pull Request sea aprobado e integrado (mergeado), pasarás oficialmente a ser un **Contribuidor de la Comunidad Linux y Open Source USM**. 
* Tu nombre y perfil de GitHub quedarán inmortalizados en el historial del proyecto.
* Tu contribución será mencionada en las Notas de Lanzamiento (Release Notes) cuando pasemos a producción.
* ¡Y por supuesto, ganarás experiencia real que podrás mostrar en tu currículum!

¡Feliz código y gracias por ser parte de la comunidad! 🐧💙
