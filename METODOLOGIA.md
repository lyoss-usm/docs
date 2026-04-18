# Metodología de Trabajo

Esta es la metodología de trabajo utilizada en TODOS los proyectos de la Comunidad Linux y Open Source. Una metodología se define básicamente como una secuencia de pasos ordenados, desde la concepción de una idea hasta su despliegue final. Aplicar esto es estrictamente necesario en nuestros proyectos por tres motivos principales:

1. **Somos estudiantes:** El tiempo efectivo que podemos dedicar al desarrollo de proyectos es limitado. Una buena organización hace que nuestro trabajo sea eficiente, evita la frustración y asegura que las ideas no queden abandonadas a mitad de semestre.
2. **Es el estándar de la industria:** En el mundo profesional, todo desarrollo de software utiliza metodologías estructuradas. Al establecer y practicar nuestro propio flujo de trabajo, te estamos brindando herramientas de gestión y habilidades blandas indispensables para el campo laboral.

---

## Fase 0: Ideación

Todo gran proyecto de código abierto nace de una idea, pero las ideas sin estructura se desvanecen. Antes de crear repositorios o escribir la primera línea de código, el proyecto debe ser pensado y justificado. 

Para esto utilizamos un enfoque basado en **RFC (Request for Comments)**.

### Pasos de la Fase 0:

**1. Redacción de la Propuesta**  
Cualquier miembro con una idea (que asumirá el rol inicial de Jefe de Proyecto) debe rellenar la [**Plantilla RFC**](https://github.com/lyoss-usm/docs/blob/main/RFC.md) oficial de la comunidad. Este documento te obligará a definir el problema, delimitar el alcance mínimo viable (MVP) y esbozar la arquitectura técnica. 

**2. Envío de la Propuesta**  
El documento Markdown rellenado debe ser enviado al Coordinador de Proyectos en actividad, cuyo método de contacto lo puedes encontrar en nuestra [Página Web](https://lyoss.org/nosotros).

**3. Revisión, Debate y Feedback**  
Los coordinadores y otros miembros leerán el RFC. De haber consultas o preguntas, el Coordinador de Proyectos en actividad te contactará para poder solicitarte más información.

**4. Aprobación Oficial**  
Una vez que el proyecto tiene un alcance realista, aporta valor real y el diseño conceptual tiene sentido, la coordinación cambiará el estado del RFC a `Aprobado`. 

```mermaid
graph TD
    A[Idea del Estudiante] --> B(1. Redactar RFC en Plantilla)
    B --> C(2. Enviar a Coordinador)
    C --> D{3. Revisión y Debate}
    D -->|Requiere Cambios / Feedback| B
    D -->|Cumple Requisitos| E((4. RFC Aprobado))
    E --> F[Inicio de Fase 1: Planificación]
    
    style E fill:#2ecc71,stroke:#27ae60,stroke-width:2px,color:white
    style D fill:#f39c12,stroke:#e67e22,stroke-width:2px,color:white
```

---

## Fase 1: Planificación y Configuración Inicial

Una vez que el RFC ha sido `Aprobado`, el Jefe de Proyecto asume la responsabilidad de liderar. Un líder no solo programa, sino que prepara el terreno para que otros puedan aportar.

### Pasos de la Fase 1:

**1. Configuración del Repositorio**  
Crea el nuevo repositorio usando [lyoss-usm/template](https://github.com/lyoss-usm/template) como base.
Al iniciar asegurate de ejecutar el workflow *Setup Repo Labels and Rulesets* en la Pestaña de **Actions**.

<img width="1315" height="329" alt="image" src="https://github.com/user-attachments/assets/17391837-aace-4ce2-8c61-440859cdbe0a" />

Una vez ejecutado el workflow, debes crear la rama `dev` y `chore/init` a partir de `main`. Esta ultima rama es para inicializar el proyecto, aqui debes:
* **Modificar README.md**
* **Subir Documento RFC a la Raiz**
* **(Opcional) Agregar archivos o informacion que consideres relevante**

Al terminar, abre un Pull Request hacia `dev` para la revision inicial. No olvides notificar por **discord** en el canal correspondiente.

**2. Desglose y Creación de Issues**  
El Jefe de Proyecto es el encargado de crear los *Issues* (tareas atómicas). Utilizamos una **Plantilla de Issue** ya predefinida en GitHub:
* **Historia de Usuario:** "*Como [Usuario] Quiero [Lograr algo] Para [Obtener un beneficio]*".
* **Criterios de Aceptación:** Checklist con las condiciones exactas para considerar la tarea terminada.
* **Tareas de Desarrollo:** Lista técnica de pasos a implementar.

**3. Uso de Etiquetas**  
Cada Issue debe ser categorizado para organizar el tablero y el Changelog:
* `Bug`: Reportes de errores o fallos en el codigo que afectan el funcionamiento esperado.
* `Fix`: Solucion a un Bug/Error.
* `Funcionalidad`: Historia de Usuario que representa un requisito funcional.
* `Documentacion`: Cambios en la documentacion sin cambios en la funcionalidad.
* `Release`: Cambios que van a produccion. (Esta etiqueta oculta PRs del changelog)
* `Good First Issue`: Úsala para tareas muy sencillas. Es para committers con poca o nada de experiencia.
* `Help Wanted`: Tareas que necesiten atencion extra.
* `Tarea Tecnica`: Se tiene que realizar para continuar con el desarrollo. (Ej: setup del proyecto base o cambios en la configuracion)
* `Test`: Pruebas de funcionamiento.

**4. Asignación y Tablero (Metodologia Kanban)**
Para evitar reuniones largas y aburridas, foomentamos el hecho de que cada colaborador se autoasigne una tarea segun su disposición de tiempo y conocimiento. El flujo del tablero es:
* **No preparada:** Aun no estan listas para ser tomadas.
* **Pendientes:** Listas para ser tomadas.
* **En progreso:** Alguien ya está trabajando en esto.
* **En revision:** Esperando revisión (PR abierta).
* **Finalizadas:** Tarea finalizada e integrada.

> [!IMPORTANT]
> El tablero del repositorio debe usar la plantilla [Lyoss Kanban Template](https://github.com/orgs/lyoss-usm/projects/13/views/1)
> <img width="964" height="335" alt="image" src="https://github.com/user-attachments/assets/8710ccf6-d5b1-4dea-bbdc-32b73f7a3282" />


**5. Búsqueda Activa de Colaboradores**  
Si bien la comunidad de Lyoss USM hace llamados generales para participar, **es vital que el Jefe de Proyecto busque activamente talento**. No esperes a que la gente adivine que tu proyecto existe. Promociona tus Issues en los grupos, invita directamente a compañeros a resolver tareas pequeñas y sé un mentor. La comunidad te dará todas las plataformas, pero la motivación del equipo depende de ti. ([Guía: Cómo encontrar usuarios y colaboradores](https://opensource.guide/es/finding-users/)).

---

## Fase 2: Flujo de Desarrollo

Utilizamos un modelo basado en ramas y [**Conventional Commits**](https://www.conventionalcommits.org/es/v1.0.0/) para evitar conflictos y mantener un historial profesional.

### Pasos de la Fase 2:

**1. Ramas Principales**  
**Jamás debes hacer un *push* directo a estas ramas protegidas:**
* **`main`**: Código en producción, versión estable.
* **`dev`**: Rama de integración donde aterrizan las nuevas características.

**2. Creación de la Rama de Trabajo**  
Crea tu rama local siempre desde `dev`. Usa nombres descriptivos en minúsculas y con guiones:
* `feature/nombre-corto`
* `fix/nombre-error`
* `docs/nombre-documento`

**3. Commits Semánticos**  
En nuestra comunidad usamos el estándar de [**Commits Convencionales (Semantic Commits)**](https://www.conventionalcommits.org/es/v1.0.0/). El mensaje debe ser corto, al grano y explicar la naturaleza del cambio:
* `feat: agrega buscador de salas`
* `fix: corrige validación de login`
* `docs: actualiza README`
* `refactor: formatea código`
* `test: agrega pruebas unitarias`

---

## Fase 3: Revisión e Integración (Pull Requests)

### Pasos de la Fase 3:

**1. Apertura del Pull Request (PR)**  
Abre un PR apuntando siempre a la rama `dev`.

**2. Rellenar la Plantilla Automática**  
Completa la plantilla de PR obligatoria de GitHub. Para cerrar el Issue automáticamente al aprobar el PR, usa palabras clave como `Closes #15`.

**3. Revisión de Código (Code Review)**  
**Nadie aprueba su propio código.** Espera a que un *Maintainer* o el *Jefe de Proyecto* lo revise. Si hay correcciones, haz nuevos commits en tu rama. Si todo está bien, se aprueba y se une a `dev` seleccionando **Squash and Merge**.

---

## Fase 4: Producción y Releases

### Pasos de la Fase 4 (Exclusivo para Jefes de Proyecto):

**1. Preparación de la Release**  
Crea un PR desde `dev` apuntando a `main`.

2. **Uso Obligatorio de la Etiqueta `Release`**
Antes de hacer el merge, debes asignar la etiqueta **Release** al Pull Request. * ¿Para qué sirve? Esta etiqueta le indica a nuestro sistema de automatización que este PR no es una simple mejora, sino un salto de versión. Evitando duplicacion en la documentacion del CHANGELOG.

3. **Integración Final**
Al unir `dev` con `main`, selecciona **Create a merge commit**. Esto mantendrá un historial claro de cuándo ocurrió cada release en la línea de tiempo del proyecto.

---

## 📚 Recursos y Lecturas para Jefes de Proyecto

Liderar un proyecto de software libre va mucho más allá del código. Te recomendamos encarecidamente revisar estas guías para formar una comunidad sana y un proyecto exitoso:

* [**The Apache Way**](https://theapacheway.com/): Entiende la filosofía de "Comunidad sobre Código" y cómo se logran los consensos.
* [**Iniciando un Proyecto Open Source**](https://opensource.guide/es/starting-a-project/): Cómo preparar tu repositorio antes de invitar a otros.
* [**Liderazgo y Gobernanza**](https://opensource.guide/es/leadership-and-governance/): Cómo tomar decisiones difíciles cuando el equipo no se pone de acuerdo.
* [**Construyendo Comunidades Acogedoras**](https://opensource.guide/es/best-practices/): Mejores prácticas para que los colaboradores no se vayan.
* [**Seguridad en Proyectos**](https://opensource.guide/es/security-best-practices-for-your-project/): Cómo evitar que datos sensibles terminen expuestos en el repositorio.
