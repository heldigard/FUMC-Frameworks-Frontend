# ⚡ Clase 2: JavaScript Interactivo y Consumo de APIs

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://miro.medium.com/v2/resize:fit:1400/1*LyZcwuLWv2FArOumCxobpA.png" alt="JavaScript">
</div>

## 🎯 Objetivos de aprendizaje
- ⚡ Entender qué es JavaScript y su rol en la web
- 🎮 Hacer páginas interactivas con eventos (clicks, inputs)
- 📝 Trabajar con formularios y validaciones
- 🌐 Consumir APIs con fetch (conectar con backend)
- 🔄 Mostrar datos dinámicamente en la página
- 🚀 Preparar terreno para Vue.js (próximas clases)

---

## ⚡ ¿Qué es JavaScript?

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://www.devopsschool.com/blog/wp-content/uploads/2022/03/javascript_logo.png" alt="JavaScript Logo">
</div>

**JavaScript (JS)** es el lenguaje de programación que hace las páginas web **interactivas**.

### 🤔 ¿Para qué sirve?
- ✅ Responder a **acciones del usuario** (clicks, escribir, mover el mouse)
- ✅ **Validar formularios** antes de enviarlos
- ✅ **Modificar el contenido** de la página sin recargar
- ✅ **Comunicarse con servidores** (APIs - como el backend que hicieron)
- ✅ Crear **animaciones y efectos**

### 💡 Analogía completa
Si una página web fuera una casa:
- **HTML** = Estructura (paredes, puertas, ventanas)
- **CSS** = Decoración (pintura, muebles)
- **JavaScript** = Funcionalidad (electricidad, agua, puertas automáticas)

---

## 🎯 JavaScript básico - Conceptos esenciales

### 1. Variables: Guardar información

```javascript
// Variables - forma moderna
let nombre = "Juan";           // Puede cambiar
const edad = 25;               // No puede cambiar (constante)
var ciudad = "Lima";           // Forma antigua (evitar)

// Tipos de datos
let numero = 42;               // Número
let texto = "Hola";            // String (texto)
let esVerdad = true;           // Boolean (verdadero/falso)
let lista = [1, 2, 3];         // Array (lista)
let persona = {                // Objeto
    nombre: "María",
    edad: 30
};
```

### 2. Funciones: Bloques de código reutilizables

```javascript
// Función básica
function saludar(nombre) {
    return "Hola, " + nombre;
}

// Función flecha (moderna)
const saludar = (nombre) => {
    return `Hola, ${nombre}`;  // Template literal
};

// Llamar la función
let mensaje = saludar("Carlos");  // "Hola, Carlos"
```

### 3. Condicionales: Tomar decisiones

```javascript
let edad = 18;

if (edad >= 18) {
    console.log("Eres mayor de edad");
} else {
    console.log("Eres menor de edad");
}
```

### 4. Bucles: Repetir acciones

```javascript
// For - repetir un número específico de veces
for (let i = 0; i < 5; i++) {
    console.log("Número: " + i);
}

// For...of - recorrer un array
let frutas = ["manzana", "banana", "naranja"];
for (let fruta of frutas) {
    console.log(fruta);
}
```

---

## 🎮 Interacción con el DOM

**DOM** = **D**ocument **O**bject **M**odel (Modelo de Objetos del Documento)

Es la representación de tu HTML que JavaScript puede **manipular**.

### 🔍 Seleccionar elementos

```javascript
// Por ID
let titulo = document.getElementById("miTitulo");

// Por clase
let botones = document.getElementsByClassName("btn");

// Por selector CSS (más usado)
let titulo = document.querySelector("#miTitulo");        // ID
let boton = document.querySelector(".btn");              // Primera clase
let botones = document.querySelectorAll(".btn");         // Todas las clases
```

### ✏️ Modificar contenido

```javascript
// Cambiar texto
let titulo = document.querySelector("h1");
titulo.textContent = "Nuevo título";

// Cambiar HTML
let contenedor = document.querySelector("#contenido");
contenedor.innerHTML = "<p>Nuevo párrafo</p>";

// Cambiar estilos
titulo.style.color = "blue";
titulo.style.fontSize = "30px";

// Agregar/quitar clases CSS
titulo.classList.add("destacado");
titulo.classList.remove("oculto");
titulo.classList.toggle("activo");  // Si existe la quita, si no la agrega
```

### 🎯 Eventos: Responder a acciones

```javascript
// Evento de click
let boton = document.querySelector("#miBoton");
boton.addEventListener("click", function() {
    alert("¡Hiciste click!");
});

// Con función flecha (más común)
boton.addEventListener("click", () => {
    alert("¡Hiciste click!");
});

// Evento de input (escribir en un campo)
let input = document.querySelector("#nombre");
input.addEventListener("input", (evento) => {
    console.log("Escribiste:", evento.target.value);
});
```

---

## 💻 Actividad práctica 1: Página interactiva (30 min)

### 🎯 Objetivo
Crear una página que responda a clicks y cambios en inputs.

### Paso 1: Crear estructura

Crea una carpeta `clase2-javascript` y un archivo `index.html`:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Interactivo</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
            max-width: 500px;
            width: 100%;
        }
        
        h1 {
            color: #2c3e50;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .section {
            margin-bottom: 30px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 10px;
        }
        
        h2 {
            color: #667eea;
            font-size: 20px;
            margin-bottom: 15px;
        }
        
        input {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            margin-bottom: 10px;
        }
        
        input:focus {
            outline: none;
            border-color: #667eea;
        }
        
        button {
            background: #667eea;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        button:hover {
            background: #764ba2;
            transform: translateY(-2px);
        }
        
        .resultado {
            margin-top: 15px;
            padding: 15px;
            background: white;
            border-radius: 8px;
            border-left: 4px solid #667eea;
            display: none;
        }
        
        .resultado.mostrar {
            display: block;
        }
        
        #contador {
            font-size: 48px;
            font-weight: bold;
            color: #667eea;
            text-align: center;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>⚡ JavaScript Interactivo</h1>
        
        <!-- Sección 1: Contador -->
        <div class="section">
            <h2>🔢 Contador</h2>
            <div id="contador">0</div>
            <button id="btnIncrementar">➕ Incrementar</button>
            <button id="btnDecrementar">➖ Decrementar</button>
            <button id="btnReiniciar">🔄 Reiniciar</button>
        </div>
        
        <!-- Sección 2: Saludo personalizado -->
        <div class="section">
            <h2>👋 Saludo personalizado</h2>
            <input type="text" id="inputNombre" placeholder="Escribe tu nombre...">
            <button id="btnSaludar">Saludar</button>
            <div id="resultadoSaludo" class="resultado"></div>
        </div>
        
        <!-- Sección 3: Cambiar color -->
        <div class="section">
            <h2>🎨 Cambiar color de fondo</h2>
            <button id="btnAzul">Azul</button>
            <button id="btnVerde" style="background: #27ae60;">Verde</button>
            <button id="btnRojo" style="background: #e74c3c;">Rojo</button>
        </div>
    </div>
    
    <!-- AQUÍ VA EL JAVASCRIPT -->
    <script>
        // ========== SECCIÓN 1: CONTADOR ==========
        let contador = 0;
        const displayContador = document.querySelector("#contador");
        const btnIncrementar = document.querySelector("#btnIncrementar");
        const btnDecrementar = document.querySelector("#btnDecrementar");
        const btnReiniciar = document.querySelector("#btnReiniciar");
        
        // Función para actualizar el display
        function actualizarContador() {
            displayContador.textContent = contador;
        }
        
        // Eventos
        btnIncrementar.addEventListener("click", () => {
            contador++;
            actualizarContador();
        });
        
        btnDecrementar.addEventListener("click", () => {
            contador--;
            actualizarContador();
        });
        
        btnReiniciar.addEventListener("click", () => {
            contador = 0;
            actualizarContador();
        });
        
        
        // ========== SECCIÓN 2: SALUDO ==========
        const inputNombre = document.querySelector("#inputNombre");
        const btnSaludar = document.querySelector("#btnSaludar");
        const resultadoSaludo = document.querySelector("#resultadoSaludo");
        
        btnSaludar.addEventListener("click", () => {
            const nombre = inputNombre.value;
            
            if (nombre === "") {
                resultadoSaludo.innerHTML = "❌ Por favor escribe tu nombre";
                resultadoSaludo.style.borderLeftColor = "#e74c3c";
            } else {
                resultadoSaludo.innerHTML = `👋 ¡Hola, <strong>${nombre}</strong>! Bienvenido.`;
                resultadoSaludo.style.borderLeftColor = "#27ae60";
            }
            
            resultadoSaludo.classList.add("mostrar");
        });
        
        // También saludar al presionar Enter
        inputNombre.addEventListener("keypress", (evento) => {
            if (evento.key === "Enter") {
                btnSaludar.click();
            }
        });
        
        
        // ========== SECCIÓN 3: CAMBIAR COLOR ==========
        const btnAzul = document.querySelector("#btnAzul");
        const btnVerde = document.querySelector("#btnVerde");
        const btnRojo = document.querySelector("#btnRojo");
        
        btnAzul.addEventListener("click", () => {
            document.body.style.background = "linear-gradient(135deg, #667eea 0%, #764ba2 100%)";
        });
        
        btnVerde.addEventListener("click", () => {
            document.body.style.background = "linear-gradient(135deg, #27ae60 0%, #16a085 100%)";
        });
        
        btnRojo.addEventListener("click", () => {
            document.body.style.background = "linear-gradient(135deg, #e74c3c 0%, #c0392b 100%)";
        });
    </script>
</body>
</html>
```

### 👀 Probar la página

1. **Abre** `index.html` en el navegador
2. **Prueba:**
   - Incrementar/decrementar el contador
   - Escribir tu nombre y hacer click en "Saludar"
   - Presionar Enter después de escribir tu nombre
   - Cambiar los colores de fondo

### 🎯 Retos adicionales

Intenta agregar estas funcionalidades:

1. **Doble del número:** Agregar un botón que multiplique el contador por 2
2. **Validación de nombre:** No permitir números en el campo de nombre
3. **Color personalizado:** Agregar un input de color para elegir el fondo

---

## 🌐 Consumiendo APIs con JavaScript

### 🤔 ¿Qué es fetch?

`fetch` es la forma moderna de hacer peticiones HTTP en JavaScript.

```javascript
// Estructura básica
fetch("URL_DE_LA_API")
    .then(respuesta => respuesta.json())  // Convertir a JSON
    .then(datos => {
        console.log(datos);  // Hacer algo con los datos
    })
    .catch(error => {
        console.error("Error:", error);
    });
```

### 📝 Métodos HTTP con fetch

```javascript
// GET - Obtener datos
fetch("https://api.ejemplo.com/usuarios")
    .then(res => res.json())
    .then(datos => console.log(datos));

// POST - Crear datos
fetch("https://api.ejemplo.com/usuarios", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({
        nombre: "Juan",
        email: "juan@ejemplo.com"
    })
})
    .then(res => res.json())
    .then(datos => console.log(datos));

// PUT - Actualizar datos
fetch("https://api.ejemplo.com/usuarios/1", {
    method: "PUT",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({
        nombre: "Juan Actualizado"
    })
})
    .then(res => res.json())
    .then(datos => console.log(datos));

// DELETE - Eliminar datos
fetch("https://api.ejemplo.com/usuarios/1", {
    method: "DELETE"
})
    .then(res => res.json())
    .then(datos => console.log(datos));
```

---

## 💻 Actividad práctica 2: Consumir una API pública (30 min)

### 🎯 Objetivo
Consumir una API de Rick and Morty para mostrar personajes.

### Paso 1: HTML básico

Crea `clase2-api-rick-morty/index.html`:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rick and Morty API</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #1e272e;
            color: white;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        h1 {
            text-align: center;
            color: #00d9ff;
            margin-bottom: 30px;
            font-size: 36px;
        }
        
        .controles {
            text-align: center;
            margin-bottom: 30px;
        }
        
        button {
            background: #00d9ff;
            color: #1e272e;
            border: none;
            padding: 12px 24px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            margin: 0 5px;
            transition: all 0.3s;
        }
        
        button:hover {
            background: #97ff00;
            transform: scale(1.05);
        }
        
        .loading {
            text-align: center;
            font-size: 24px;
            color: #00d9ff;
        }
        
        .personajes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .card {
            background: #2c3e50;
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s;
        }
        
        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.3);
        }
        
        .card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }
        
        .card-info {
            padding: 15px;
        }
        
        .card h3 {
            color: #00d9ff;
            margin-bottom: 10px;
        }
        
        .card p {
            color: #bdc3c7;
            margin-bottom: 5px;
        }
        
        .status {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
        }
        
        .status.alive {
            background: #27ae60;
            color: white;
        }
        
        .status.dead {
            background: #e74c3c;
            color: white;
        }
        
        .status.unknown {
            background: #95a5a6;
            color: white;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🛸 Rick and Morty API</h1>
        
        <div class="controles">
            <button id="btnCargar">Cargar Personajes</button>
            <button id="btnLimpiar">Limpiar</button>
        </div>
        
        <div id="loading" class="loading" style="display: none;">
            ⏳ Cargando personajes...
        </div>
        
        <div id="personajes" class="personajes-grid"></div>
    </div>
    
    <script>
        const btnCargar = document.querySelector("#btnCargar");
        const btnLimpiar = document.querySelector("#btnLimpiar");
        const personajesDiv = document.querySelector("#personajes");
        const loadingDiv = document.querySelector("#loading");
        
        // Función para cargar personajes
        async function cargarPersonajes() {
            // Mostrar loading
            loadingDiv.style.display = "block";
            personajesDiv.innerHTML = "";
            
            try {
                // Hacer petición a la API
                const respuesta = await fetch("https://rickandmortyapi.com/api/character");
                const datos = await respuesta.json();
                
                // Ocultar loading
                loadingDiv.style.display = "none";
                
                // Mostrar personajes
                mostrarPersonajes(datos.results);
                
            } catch (error) {
                console.error("Error:", error);
                loadingDiv.textContent = "❌ Error al cargar personajes";
            }
        }
        
        // Función para mostrar personajes en el DOM
        function mostrarPersonajes(personajes) {
            personajesDiv.innerHTML = "";
            
            personajes.forEach(personaje => {
                const card = document.createElement("div");
                card.className = "card";
                
                // Determinar clase de status
                let statusClass = personaje.status.toLowerCase();
                
                card.innerHTML = `
                    <img src="${personaje.image}" alt="${personaje.name}">
                    <div class="card-info">
                        <h3>${personaje.name}</h3>
                        <p><span class="status ${statusClass}">${personaje.status}</span></p>
                        <p><strong>Especie:</strong> ${personaje.species}</p>
                        <p><strong>Género:</strong> ${personaje.gender}</p>
                        <p><strong>Origen:</strong> ${personaje.origin.name}</p>
                    </div>
                `;
                
                personajesDiv.appendChild(card);
            });
        }
        
        // Función para limpiar
        function limpiar() {
            personajesDiv.innerHTML = "";
            loadingDiv.style.display = "none";
        }
        
        // Eventos
        btnCargar.addEventListener("click", cargarPersonajes);
        btnLimpiar.addEventListener("click", limpiar);
    </script>
</body>
</html>
```

### 👀 Probar

1. Abre el archivo en el navegador
2. Click en "Cargar Personajes"
3. Observa cómo se cargan los personajes desde la API
4. Pasa el mouse sobre las tarjetas para ver el efecto hover

### 🎯 Código explicado

```javascript
// async/await - forma moderna de manejar promesas
async function cargarPersonajes() {
    try {
        // await espera a que la petición termine
        const respuesta = await fetch("URL");
        const datos = await respuesta.json();
        
        // Hacer algo con los datos
        mostrarPersonajes(datos.results);
        
    } catch (error) {
        // Si hay error, lo capturamos aquí
        console.error(error);
    }
}
```

---

## 💻 Actividad práctica 3: CRUD básico con tu API de FastAPI (40 min)

### 🎯 Objetivo
Conectar con la API de tareas que crearon en backend.

### ⚠️ Importante: CORS

Primero, debes agregar CORS a tu API de FastAPI:

```python
# En tu main.py de FastAPI
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI()

# Configurar CORS
app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],  # En producción, especifica el dominio exacto
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

### Paso 1: HTML con formulario

Crea `clase2-crud-tareas/index.html`:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestor de Tareas</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        }
        
        h1 {
            color: #2c3e50;
            text-align: center;
            margin-bottom: 30px;
        }
        
        .formulario {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 30px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        label {
            display: block;
            color: #2c3e50;
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        input, textarea {
            width: 100%;
            padding: 10px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 14px;
        }
        
        input:focus, textarea:focus {
            outline: none;
            border-color: #667eea;
        }
        
        textarea {
            resize: vertical;
            min-height: 80px;
        }
        
        button {
            background: #667eea;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        button:hover {
            background: #764ba2;
            transform: translateY(-2px);
        }
        
        .lista-tareas {
            list-style: none;
        }
        
        .tarea-item {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }
        
        .tarea-item:hover {
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }
        
        .tarea-item.completada {
            background: #d5f4e6;
        }
        
        .tarea-info h3 {
            color: #2c3e50;
            margin-bottom: 5px;
        }
        
        .tarea-info p {
            color: #7f8c8d;
            font-size: 14px;
        }
        
        .tarea-item.completada h3 {
            text-decoration: line-through;
            color: #95a5a6;
        }
        
        .tarea-acciones button {
            margin-left: 5px;
            padding: 8px 16px;
            font-size: 14px;
        }
        
        .btn-completar {
            background: #27ae60;
        }
        
        .btn-completar:hover {
            background: #229954;
        }
        
        .btn-eliminar {
            background: #e74c3c;
        }
        
        .btn-eliminar:hover {
            background: #c0392b;
        }
        
        .loading {
            text-align: center;
            color: #667eea;
            font-size: 18px;
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>📝 Gestor de Tareas</h1>
        
        <!-- Formulario para crear tarea -->
        <div class="formulario">
            <h2>➕ Nueva Tarea</h2>
            <form id="formTarea">
                <div class="form-group">
                    <label for="titulo">Título:</label>
                    <input type="text" id="titulo" required>
                </div>
                
                <div class="form-group">
                    <label for="descripcion">Descripción:</label>
                    <textarea id="descripcion" required></textarea>
                </div>
                
                <button type="submit">Crear Tarea</button>
            </form>
        </div>
        
        <!-- Lista de tareas -->
        <div id="loading" class="loading" style="display: none;">
            ⏳ Cargando tareas...
        </div>
        
        <ul id="listaTareas" class="lista-tareas"></ul>
    </div>
    
    <script>
        // URL de tu API (CAMBIA ESTO por tu URL de FastAPI)
        const API_URL = "http://127.0.0.1:8000/tareas";
        
        // Elementos del DOM
        const formTarea = document.querySelector("#formTarea");
        const listaTareas = document.querySelector("#listaTareas");
        const loadingDiv = document.querySelector("#loading");
        
        // Variable para almacenar ID de tarea (empieza en 4 porque ya hay 3 de ejemplo)
        let proximoId = 4;
        
        // ========== CARGAR TAREAS AL INICIAR ==========
        cargarTareas();
        
        // ========== FUNCIÓN: CARGAR TODAS LAS TAREAS ==========
        async function cargarTareas() {
            loadingDiv.style.display = "block";
            listaTareas.innerHTML = "";
            
            try {
                const respuesta = await fetch(API_URL);
                const tareas = await respuesta.json();
                
                loadingDiv.style.display = "none";
                
                // Actualizar proximoId
                if (tareas.length > 0) {
                    const maxId = Math.max(...tareas.map(t => t.id));
                    proximoId = maxId + 1;
                }
                
                tareas.forEach(tarea => mostrarTarea(tarea));
                
            } catch (error) {
                console.error("Error al cargar tareas:", error);
                loadingDiv.textContent = "❌ Error al cargar tareas";
            }
        }
        
        // ========== FUNCIÓN: CREAR TAREA ==========
        formTarea.addEventListener("submit", async (e) => {
            e.preventDefault();  // Evitar que se recargue la página
            
            const titulo = document.querySelector("#titulo").value;
            const descripcion = document.querySelector("#descripcion").value;
            
            const nuevaTarea = {
                id: proximoId,
                titulo: titulo,
                descripcion: descripcion,
                completada: false
            };
            
            try {
                const respuesta = await fetch(API_URL + "/", {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json"
                    },
                    body: JSON.stringify(nuevaTarea)
                });
                
                const tareaCreada = await respuesta.json();
                
                // Limpiar formulario
                formTarea.reset();
                
                // Actualizar ID
                proximoId++;
                
                // Recargar tareas
                cargarTareas();
                
            } catch (error) {
                console.error("Error al crear tarea:", error);
                alert("Error al crear la tarea");
            }
        });
        
        // ========== FUNCIÓN: MOSTRAR TAREA EN EL DOM ==========
        function mostrarTarea(tarea) {
            const li = document.createElement("li");
            li.className = `tarea-item ${tarea.completada ? 'completada' : ''}`;
            
            li.innerHTML = `
                <div class="tarea-info">
                    <h3>${tarea.titulo}</h3>
                    <p>${tarea.descripcion}</p>
                </div>
                <div class="tarea-acciones">
                    <button class="btn-completar" onclick="toggleCompletar(${tarea.id}, ${!tarea.completada})">
                        ${tarea.completada ? '↩️ Desmarcar' : '✅ Completar'}
                    </button>
                    <button class="btn-eliminar" onclick="eliminarTarea(${tarea.id})">
                        🗑️ Eliminar
                    </button>
                </div>
            `;
            
            listaTareas.appendChild(li);
        }
        
        // ========== FUNCIÓN: MARCAR/DESMARCAR COMPLETADA ==========
        async function toggleCompletar(id, completada) {
            try {
                // Primero obtenemos la tarea completa
                const respuesta = await fetch(`${API_URL}/${id}`);
                const tarea = await respuesta.json();
                
                // Actualizamos solo el campo completada
                tarea.completada = completada;
                
                // Enviamos la actualización
                await fetch(`${API_URL}/${id}`, {
                    method: "PUT",
                    headers: {
                        "Content-Type": "application/json"
                    },
                    body: JSON.stringify(tarea)
                });
                
                // Recargar tareas
                cargarTareas();
                
            } catch (error) {
                console.error("Error al actualizar tarea:", error);
                alert("Error al actualizar la tarea");
            }
        }
        
        // ========== FUNCIÓN: ELIMINAR TAREA ==========
        async function eliminarTarea(id) {
            if (!confirm("¿Estás seguro de eliminar esta tarea?")) {
                return;
            }
            
            try {
                await fetch(`${API_URL}/${id}`, {
                    method: "DELETE"
                });
                
                // Recargar tareas
                cargarTareas();
                
            } catch (error) {
                console.error("Error al eliminar tarea:", error);
                alert("Error al eliminar la tarea");
            }
        }
    </script>
</body>
</html>
```

### 🚀 Cómo usar

1. **Inicia tu API de FastAPI:**
   ```bash
   cd clase2-api-tareas
   uvicorn main:app --reload
   ```

2. **Abre** `index.html` en el navegador

3. **Prueba:**
   - Crear nuevas tareas
   - Marcar como completadas
   - Eliminar tareas

### ✅ Verificación

Si todo funciona correctamente:
- ✅ Ves las 3 tareas de ejemplo al cargar
- ✅ Puedes crear nuevas tareas
- ✅ Puedes marcar tareas como completadas
- ✅ Puedes eliminar tareas
- ✅ Los cambios persisten (se guardan en el backend)

---

## 🎯 Conceptos importantes - Async/Await

### ¿Por qué async/await?

```javascript
// ❌ Forma antigua (callback hell)
fetch(url)
    .then(res => res.json())
    .then(datos => {
        fetch(otraUrl)
            .then(res => res.json())
            .then(masDatos => {
                // ...muchos niveles
            });
    });

// ✅ Forma moderna (async/await)
async function cargarDatos() {
    const respuesta1 = await fetch(url);
    const datos1 = await respuesta1.json();
    
    const respuesta2 = await fetch(otraUrl);
    const datos2 = await respuesta2.json();
    
    // Código más limpio y legible
}
```

### Try/Catch para manejar errores

```javascript
async function cargarDatos() {
    try {
        // Código que puede fallar
        const respuesta = await fetch(url);
        const datos = await respuesta.json();
        return datos;
        
    } catch (error) {
        // Si hay error, se ejecuta esto
        console.error("Error:", error);
        alert("No se pudieron cargar los datos");
    }
}
```

---

## 📝 Resumen de la clase

### ✅ Lo que aprendimos:

1. **JavaScript básico:**
   - Variables, funciones, condicionales
   - Eventos y manipulación del DOM
   - Interactividad en tiempo real

2. **Consumo de APIs:**
   - Qué es fetch y cómo usarlo
   - GET, POST, PUT, DELETE
   - Async/await para código asíncrono
   - Manejo de errores con try/catch

3. **CRUD completo:**
   - Crear tareas (POST)
   - Leer tareas (GET)
   - Actualizar tareas (PUT)
   - Eliminar tareas (DELETE)

4. **Integración frontend-backend:**
   - Conectar HTML/JS con API de FastAPI
   - CORS y su importancia
   - Actualización dinámica del DOM

---

## 🎯 Entregable de la clase

### Checklist:

✅ **Actividad 1: Página interactiva**
- Contador funcional
- Saludo personalizado con validación
- Cambio de colores

✅ **Actividad 2: Rick and Morty API**
- Carga de personajes desde API pública
- Visualización en tarjetas

✅ **Actividad 3: CRUD de tareas**
- Conexión con tu API de FastAPI
- Crear, leer, actualizar y eliminar tareas
- Todo funcionando correctamente

### 📤 Subir a GitHub

```bash
git add .
git commit -m "Clase 2: JavaScript y consumo de APIs"
git push
```

---

## 🚀 Próximas clases

### Clase 3: Introducción a Vue.js
- ¿Qué es Vue.js y por qué usarlo?
- Sintaxis de templates
- Directivas: v-for, v-if, v-model
- Componentes básicos

### Clase 4: CRUD con Vue.js
- Crear aplicación completa con Vue
- Consumir tu API de FastAPI desde Vue
- Componentes reutilizables
- Preparar para deploy

---

## 💡 Recursos adicionales

### 📚 Documentación
- **MDN JavaScript:** https://developer.mozilla.org/es/docs/Web/JavaScript
- **JavaScript.info:** https://javascript.info/
- **Fetch API:** https://developer.mozilla.org/es/docs/Web/API/Fetch_API

### 🎮 APIs públicas para practicar
- **Rick and Morty:** https://rickandmortyapi.com/
- **JSONPlaceholder:** https://jsonplaceholder.typicode.com/
- **PokeAPI:** https://pokeapi.co/
- **Star Wars:** https://swapi.dev/

### 🛠️ Herramientas
- **JSON Viewer:** Extensión para Chrome/Firefox
- **Console del navegador:** F12 → Console
- **Network tab:** F12 → Network (ver peticiones HTTP)

---

## 🎉 ¡Felicidades!

Has dado un paso enorme:
- ✅ Dominas JavaScript básico
- ✅ Sabes consumir APIs con fetch
- ✅ Puedes crear aplicaciones CRUD completas
- ✅ Entiendes la integración frontend-backend

**Próximo paso:** Aprender Vue.js para crear aplicaciones más robustas y escalables.

---

**Última actualización:** Octubre 2025  
**Versión:** 1.0
