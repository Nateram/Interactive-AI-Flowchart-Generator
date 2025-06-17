# Interactive AI Flowchart Generator / Generador Interactivo de Diagramas de Flujo con IA

<div id="lang-selector" align="center">
  <a href="#english-documentation">English Documentation</a> | <a href="#documentacion-espanol">Documentación en Español</a>
</div>

---

<div id="english-documentation">

## English Documentation

**Author:** Pablo Natera Muñoz

**Background:** Graduate in Computer Engineering with a specialization in Software Engineering from UEX (University of Extremadura).

### 📖 Overview

This project is a single-file HTML web application that allows users to create, visualize, and interact with flowcharts. A key feature is its ability to generate flowcharts automatically from a textual description using the Google Gemini AI API. The application is designed to be highly interactive, allowing users to manipulate nodes and connections, customize their appearance, and export the final diagram in SVG format for a high-quality, scalable output.

### ✨ Features

*   **AI-Powered Generation:** Describe a process, and the application (using Google Gemini API) will generate a preliminary flowchart.
*   **Interactive Canvas:**
    *   **Drag & Drop Nodes:** Easily reposition nodes on the canvas.
    *   **Create Connections:** Visually link nodes by clicking on their connection points.
    *   **Edit Elements:**
        *   Modify node text.
        *   Change node colors.
        *   Edit connection labels.
        *   Adjust connection anchor points (from/to points on nodes).
    *   **Selection & Deletion:** Select nodes or connections to modify or delete them.
*   **Curved Connections:** Connections between nodes are rendered as smooth quadratic Bézier curves.
*   **Dynamic SVG Canvas:** The SVG canvas automatically resizes to fit the content, with scrollbars for large diagrams.
*   **SVG Export:** Export your flowchart as an SVG file, preserving quality and scalability.
*   **API Key Management:**
    *   Securely stores your Google Gemini API Key in the browser's `localStorage`.
    *   Prompts for an API key if one is not found.
*   **Single-File Application:** The entire application (HTML, CSS, JavaScript) is contained within a single `.html` file for maximum portability.
*   **User-Friendly Interface:**
    *   Intuitive controls and modals for various actions.
    *   Context menu (right-click) for quick access to element-specific operations.
    *   Visual feedback for selections and interactions.

### 🛠️ Technology Stack

*   **Frontend:** HTML5, CSS3, Vanilla JavaScript (ES6+)
*   **Graphics:** SVG (Scalable Vector Graphics) for rendering the flowchart.
*   **AI Integration:** Google Gemini API (specifically `gemini-1.5-flash-latest` model via its REST API).

### 🚀 How to Use

1.  **Open the HTML File:** Simply open the `.html` file in any modern web browser.
2.  **Set API Key (First Time):**
    *   If you haven't set your Google Gemini API Key, a modal will appear.
    *   You can also click the "API Key" button in the header.
    *   Enter your valid API key and save. It will be stored in your browser's `localStorage` for future sessions.
3.  **Generate with AI:**
    *   Click the "Generate with AI" button.
    *   Describe the process or workflow you want to diagram in the text area.
    *   Click "Generate". The AI will process your description and create an initial flowchart.
4.  **Manual Interaction:**
    *   **Move Nodes:** Click and drag a node.
    *   **Select:** Click on a node or a connection line. Selected elements will be highlighted.
    *   **Edit Text/Properties:**
        *   Double-click a node to edit its text.
        *   Double-click a connection or its label to edit the label and anchor points.
        *   Right-click a selected node to change its color or edit text.
        *   Right-click a selected connection to edit its properties.
    *   **Add Connections:**
        *   Click the "Connect Nodes" button. Connection points on nodes will become more visible.
        *   Click a connection point on a source node.
        *   Click a connection point on a target node.
        *   Right-click or press `ESC` to cancel connection mode.
    *   **Delete:** Select an element and press the `Delete` or `Backspace` key, or use the context menu.
5.  **Export:**
    *   Click the "Export SVG" button to download the current flowchart as an `.svg` file.
6.  **Clear Canvas:**
    *   Click the "Clear" button to remove all elements from the canvas.

### 🔧 Setup & Configuration

*   **Google Gemini API Key:** You need a valid API key from Google AI Studio (or Google Cloud with the Generative Language API enabled). Ensure the API key has permissions to use the Gemini models.
*   **Modern Browser:** Recommended browsers are Chrome, Firefox, Edge, or Safari (latest versions).

### 🏗️ Code Structure (Brief)

The entire application resides in a single HTML file:

*   **`<style>` section:** Contains all CSS rules for styling the application, including UI elements and SVG components.
*   **HTML body:** Defines the layout, buttons, modals, and the main SVG canvas.
*   **`<script>` section:** Contains all the JavaScript logic:
    *   **Global Variables & Constants:** For SVG namespace, UI elements, application state.
    *   **CSS Variable Helper:** `getCssVariable()`
    *   **API Key Management:** Functions for storing and retrieving the API key.
    *   **Data Models:** `FlowchartNode` and `FlowchartConnection` classes.
    *   **Drawing Functions:** `drawNode()`, `drawConnection()`, `redrawAll()`, `updateSvgDimensions()`.
    *   **Event Handlers:** For mouse interactions (mousedown, mousemove, mouseup, dblclick, contextmenu) on the SVG canvas, and button clicks.
    *   **Modal Logic:** Functions to show/hide and manage input from modals.
    *   **Context Menu Logic:** Functions to display and handle context menu actions.
    *   **AI Integration:** `submit-ai-prompt-btn` click handler, which constructs the prompt, calls the Gemini API, and processes the JSON response.
    *   **SVG Export Logic:** Handles cloning the SVG, embedding necessary styles, and triggering the download.
    *   **Utility Functions:** `getSVGCoordinates()`, `deselectAll()`, `deleteElement()`, etc.
    *   **Initialization:** Sets up initial state and event listeners.

### 💭 Future Enhancements (Ideas)

*   More sophisticated curved line routing algorithms.
*   User-draggable control points for connection curves.
*   Zoom and pan functionality for the canvas.
*   Save/Load diagram state (e.g., to/from JSON file or `localStorage`).
*   Undo/Redo functionality.
*   More node shapes and customization options.
*   Real-time collaboration (ambitious!).

### 🙏 Acknowledgements

This project leverages the power of the Google Gemini API for its AI-driven flowchart generation.

---
</div>

<div id="documentacion-espanol">

## Documentación en Español

**Autor:** Pablo Natera Muñoz

**Formación:** Graduado en Ingeniería Informática en Ingeniería del Software por la UEX (Universidad de Extremadura).

### 📖 Descripción General

Este proyecto es una aplicación web en un único archivo HTML que permite a los usuarios crear, visualizar e interactuar con diagramas de flujo. Una característica clave es su capacidad para generar diagramas de flujo automáticamente a partir de una descripción textual utilizando la API de IA de Google Gemini. La aplicación está diseñada para ser altamente interactiva, permitiendo a los usuarios manipular nodos y conexiones, personalizar su apariencia y exportar el diagrama final en formato SVG para una salida escalable y de alta calidad.

### ✨ Características

*   **Generación con IA:** Describe un proceso y la aplicación (usando la API de Google Gemini) generará un diagrama de flujo preliminar.
*   **Lienzo Interactivo:**
    *   **Arrastrar y Soltar Nodos:** Reposiciona nodos fácilmente en el lienzo.
    *   **Crear Conexiones:** Vincula nodos visualmente haciendo clic en sus puntos de conexión.
    *   **Editar Elementos:**
        *   Modificar texto de los nodos.
        *   Cambiar colores de los nodos.
        *   Editar etiquetas de las conexiones.
        *   Ajustar puntos de anclaje de las conexiones (puntos de origen/destino en los nodos).
    *   **Selección y Eliminación:** Selecciona nodos o conexiones para modificarlos o eliminarlos.
*   **Conexiones Curvas:** Las conexiones entre nodos se renderizan como suaves curvas de Bézier cuadráticas.
*   **Lienzo SVG Dinámico:** El lienzo SVG se redimensiona automáticamente para ajustarse al contenido, con barras de desplazamiento para diagramas grandes.
*   **Exportación SVG:** Exporta tu diagrama de flujo como un archivo SVG, conservando la calidad y la escalabilidad.
*   **Gestión de API Key:**
    *   Almacena de forma segura tu API Key de Google Gemini en el `localStorage` del navegador.
    *   Solicita una API key si no se encuentra ninguna.
*   **Aplicación en un Solo Archivo:** Toda la aplicación (HTML, CSS, JavaScript) está contenida en un único archivo `.html` para máxima portabilidad.
*   **Interfaz Amigable:**
    *   Controles intuitivos y modales para diversas acciones.
    *   Menú contextual (clic derecho) para acceso rápido a operaciones específicas de elementos.
    *   Retroalimentación visual para selecciones e interacciones.

### 🛠️ Tecnologías Utilizadas

*   **Frontend:** HTML5, CSS3, JavaScript Vanilla (ES6+)
*   **Gráficos:** SVG (Scalable Vector Graphics) para renderizar el diagrama de flujo.
*   **Integración IA:** API de Google Gemini (específicamente el modelo `gemini-1.5-flash-latest` a través de su API REST).

### 🚀 Cómo Usar

1.  **Abrir el Archivo HTML:** Simplemente abre el archivo `.html` en cualquier navegador web moderno.
2.  **Establecer API Key (Primera Vez):**
    *   Si no has establecido tu API Key de Google Gemini, aparecerá un modal.
    *   También puedes hacer clic en el botón "API Key" en la cabecera.
    *   Introduce tu API key válida y guárdala. Se almacenará en el `localStorage` de tu navegador para futuras sesiones.
3.  **Generar con IA:**
    *   Haz clic en el botón "Generar con IA".
    *   Describe el proceso o flujo de trabajo que quieres diagramar en el área de texto.
    *   Haz clic en "Generar". La IA procesará tu descripción y creará un diagrama de flujo inicial.
4.  **Interacción Manual:**
    *   **Mover Nodos:** Haz clic y arrastra un nodo.
    *   **Seleccionar:** Haz clic en un nodo o en una línea de conexión. Los elementos seleccionados se resaltarán.
    *   **Editar Texto/Propiedades:**
        *   Doble clic en un nodo para editar su texto.
        *   Doble clic en una conexión o su etiqueta para editar la etiqueta y los puntos de anclaje.
        *   Clic derecho en un nodo seleccionado para cambiar su color o editar texto.
        *   Clic derecho en una conexión seleccionada para editar sus propiedades.
    *   **Añadir Conexiones:**
        *   Haz clic en el botón "Conectar Nodos". Los puntos de conexión en los nodos se volverán más visibles.
        *   Haz clic en un punto de conexión en un nodo de origen.
        *   Haz clic en un punto de conexión en un nodo de destino.
        *   Clic derecho o presiona `ESC` para cancelar el modo de conexión.
    *   **Eliminar:** Selecciona un elemento y presiona la tecla `Supr` o `Retroceso`, o usa el menú contextual.
5.  **Exportar:**
    *   Haz clic en el botón "Exportar SVG" para descargar el diagrama de flujo actual como un archivo `.svg`.
6.  **Limpiar Lienzo:**
    *   Haz clic en el botón "Limpiar" para eliminar todos los elementos del lienzo.

### 🔧 Configuración

*   **API Key de Google Gemini:** Necesitas una API key válida de Google AI Studio (o Google Cloud con la API de Lenguaje Generativo habilitada). Asegúrate de que la API key tenga permisos para usar los modelos Gemini.
*   **Navegador Moderno:** Se recomiendan los navegadores Chrome, Firefox, Edge o Safari (últimas versiones).

### 🏗️ Estructura del Código (Breve)

Toda la aplicación reside en un único archivo HTML:

*   **Sección `<style>`:** Contiene todas las reglas CSS para el estilo de la aplicación, incluyendo elementos de la interfaz y componentes SVG.
*   **Cuerpo HTML:** Define la disposición, botones, modales y el lienzo SVG principal.
*   **Sección `<script>`:** Contiene toda la lógica JavaScript:
    *   **Variables Globales y Constantes:** Para el espacio de nombres SVG, elementos de UI, estado de la aplicación.
    *   **Ayudante de Variables CSS:** `getCssVariable()`
    *   **Gestión de API Key:** Funciones para almacenar y recuperar la API key.
    *   **Modelos de Datos:** Clases `FlowchartNode` y `FlowchartConnection`.
    *   **Funciones de Dibujo:** `drawNode()`, `drawConnection()`, `redrawAll()`, `updateSvgDimensions()`.
    *   **Manejadores de Eventos:** Para interacciones del ratón (mousedown, mousemove, mouseup, dblclick, contextmenu) en el lienzo SVG, y clics de botones.
    *   **Lógica de Modales:** Funciones para mostrar/ocultar y gestionar la entrada de los modales.
    *   **Lógica del Menú Contextual:** Funciones para mostrar y manejar las acciones del menú contextual.
    *   **Integración con IA:** Manejador del clic de `submit-ai-prompt-btn`, que construye el prompt, llama a la API de Gemini y procesa la respuesta JSON.
    *   **Lógica de Exportación SVG:** Maneja la clonación del SVG, la incrustación de estilos necesarios y la activación de la descarga.
    *   **Funciones de Utilidad:** `getSVGCoordinates()`, `deselectAll()`, `deleteElement()`, etc.
    *   **Inicialización:** Configura el estado inicial y los escuchadores de eventos.

### 💭 Mejoras Futuras (Ideas)

*   Algoritmos más sofisticados para el enrutamiento de líneas curvas.
*   Puntos de control arrastrables por el usuario para las curvas de conexión.
*   Funcionalidad de zoom y paneo para el lienzo.
*   Guardar/Cargar estado del diagrama (ej., desde/hacia archivo JSON o `localStorage`).
*   Funcionalidad de Deshacer/Rehacer.
*   Más formas de nodos y opciones de personalización.
*   Colaboración en tiempo real (¡ambicioso!).

### 🙏 Agradecimientos

Este proyecto aprovecha la potencia de la API de Google Gemini para su generación de diagramas de flujo dirigida por IA.

---
</div>
