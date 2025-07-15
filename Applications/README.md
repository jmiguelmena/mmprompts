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
## 🟩 Aplicación Web Interactiva: El Problema del Recorrido del Caballo 🐎

Esta es una aplicación web interactiva diseñada para explorar y resolver el famoso "Problema del Recorrido del Caballo" (Knight's Tour Problem) en un tablero de ajedrez. El objetivo es encontrar una secuencia de movimientos legales de un caballo de ajedrez, de modo que visite cada casilla del tablero exactamente una vez.

## Características Principales

### 1. Tablero Personalizable
* **Tamaño del Tablero:** Permite al usuario seleccionar el tamaño del tablero, con opciones que van desde 5x5 hasta un máximo razonable de 10x10.
* **Visualización:** El tablero se visualiza claramente, con casillas alternadas (como un tablero de ajedrez tradicional) en los niveles de dificultad "Fácil" y "Medio". En el nivel "Experto", el tablero es de un solo color pero mantiene la cuadrícula visible.

### 2. Movimientos del Caballo
* **Colocación Inicial:** El usuario puede hacer clic en cualquier casilla para colocar el caballo por primera vez.
* **Movimientos Válidos:** Cuando el caballo está en una casilla, la aplicación resalta las casillas válidas a las que puede moverse (solo en el nivel "Fácil").
* **Interacción:** El usuario puede hacer clic en una de las casillas válidas para mover el caballo.
* **Registro Visual:** Cada movimiento se registra visualmente numerando las casillas en el orden de visita (del 1 al N, donde N es el total de casillas del tablero).
* **Restricciones:** No se permite al usuario mover el caballo a una casilla ya visitada.

### 3. Funcionalidades de Juego
* **Indicador de Progreso:** Muestra el número de casillas visitadas en relación con el total de casillas del tablero (e.g., "Casillas visitadas: X/Y").
* **Botón "Reiniciar Juego":** Permite al usuario iniciar un nuevo juego desde cero, manteniendo el tamaño y la dificultad seleccionados.
* **Botón "Deshacer Último Movimiento":** Permite corregir errores y volver a la posición anterior del caballo.

### 4. Niveles de Dificultad
La aplicación ofrece diferentes niveles de desafío para adaptarse a la experiencia del usuario:

* **Nivel Fácil:**
    * El juego funciona de manera asistida.
    * Muestra dónde puedes colocar el caballo.
    * Resalta los posibles movimientos válidos del caballo.
    * El tablero tiene casillas alternadas (colores de ajedrez).

* **Nivel Medio:**
    * El juego es más desafiante.
    * El tablero mantiene las casillas alternadas.
    * **No se resaltan** los posibles movimientos del caballo.

* **Nivel Experto:**
    * El nivel más difícil.
    * El tablero es de un solo color (blanco/claro).
    * **No se resaltan** los posibles movimientos del caballo.
    * La cuadrícula del tablero es visible para ayudar en la orientación.

### 5. Ayuda al Usuario (Funcionalidad Avanzada)
* **Botón "Mostrar Solución":** Integra un algoritmo (Regla de Warnsdorff) que genera y muestra una solución válida para el tamaño de tablero actual. La solución se visualiza paso a paso, permitiendo al usuario aprender o verificar un recorrido completo.

## Aspectos Técnicos / Tecnologías Utilizadas

* **Frontend:**
    * **HTML:** Para la estructura de la página.
    * **CSS:** Para el estilizado y el diseño responsivo (utilizando Tailwind CSS para utilidades y estilos personalizados).
    * **JavaScript:** Para toda la lógica interactiva del juego, la gestión del estado y la implementación del algoritmo de solución.
* **Algoritmo de Solución:** Se utiliza la **Regla de Warnsdorff**, una heurística eficiente para encontrar soluciones al Problema del Recorrido del Caballo directamente en el frontend.

## Consideraciones Adicionales

* **Diseño Responsivo:** La interfaz está optimizada para ser completamente funcional y visualmente atractiva tanto en dispositivos de escritorio como en móviles.
* **Interfaz de Usuario (UI) Intuitiva:** Se ha priorizado una UI limpia, clara y fácil de entender para una experiencia de usuario óptima.
* **Mensajes al Usuario:** La aplicación proporciona feedback claro y oportuno al usuario a través de mensajes informativos, de éxito o de error (e.g., "Movimiento inválido", "Juego completado", "No hay más movimientos posibles").

## Cómo Usar la Aplicación

1.  Guarda el código HTML proporcionado en un archivo con extensión `.html` (por ejemplo, `knight_tour.html`).
2.  Abre el archivo `.html` en tu navegador web preferido.
3.  Selecciona el tamaño del tablero y el nivel de dificultad deseado.
4.  Haz clic en una casilla para colocar el caballo y ¡comienza tu recorrido!
