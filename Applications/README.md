# Prompts para Aplicaciones Web

Este archivo contiene una colección de prompts diseñados para describir aplicaciones web específicas que pueden ser desarrolladas utilizando tecnologías modernas. Los prompts están redactados de forma precisa para servir como requerimientos funcionales para desarrolladores.

---

## 🟩 Visualización tipo Gantt simplificada (HTML, JS, Tailwind)

**Prompt:**

Solicito el desarrollo de una aplicación web de visualización tipo Gantt simplificada en una sola página, utilizando exclusivamente HTML, JavaScript (vanilla, ES6+) y Tailwind CSS (vía CDN). La interfaz se estructurará en dos columnas verticales adaptables a pantallas pequeñas: una columna izquierda fija (sticky) que presentará una lista de tareas numerada automáticamente, mostrando el nombre y la fecha objetivo (dd/mm/yyyy) de cada tarea, con scroll vertical si es necesario; y una columna derecha que contendrá la línea de tiempo principal, la cual debe permitir scroll horizontal independiente.

El aspecto clave de la línea de tiempo es su rango dinámico: la cabecera superior mostrará meses consecutivos (formato "Mes Año", ej: "Ene 25") abarcando desde la fecha más temprana hasta la más tardía encontrada en los datos de las tareas, no limitándose al año actual, y cada mes tendrá un ancho fijo con líneas guía verticales debajo.

Dentro del cuerpo scrollable de la línea de tiempo, se dibujarán barras horizontales para cada tarea válida, posicionadas horizontalmente según su `targetDate` relativo al rango dinámico total de días y apiladas verticalmente. Cada barra tendrá esquinas redondeadas, un color de fondo único (cíclico de una paleta), altura constante, mostrará internamente el nombre de la tarea y la fecha corta ("dd MMM", truncado si es preciso), y tendrá un marcador circular blanco en su extremo derecho.

La interactividad incluirá un efecto visual de realce (escala/sombra) al pasar el cursor sobre una barra y la aparición de un tooltip con `position: fixed` que muestre el nombre completo y la fecha completa en español (ej: "Lunes, 20 de enero de 2025"), ajustándose para no salirse de la pantalla.

La aplicación deberá procesar un array de objetos JavaScript con la estructura `{ id, name, targetDate: 'YYYY-MM-DD' }` como entrada, lograr un diseño moderno, limpio y responsivo con fondo claro usando Tailwind, y asegurar la localización en español para las fechas del tooltip.

**Resultado esperado:**  
Un archivo `index.html` y un archivo `script.js`.

---
