# 🎨 Clase 1: Introducción a HTML y CSS - Creando tu primera página web

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://www.oxfordwebstudio.com/user/pages/06.da-li-znate/sta-je-html/sta-je-html.jpg" alt="HTML y CSS">
</div>

## 🎯 Objetivos de aprendizaje
- 🏗️ Entender qué es HTML y su estructura básica
- 🎨 Aprender a dar estilo con CSS
- 👀 Ver cambios en tiempo real en el navegador
- 📝 Crear una página web simple y funcional
- 🔧 Preparar el entorno para desarrollo frontend

---

## 🌐 ¿Qué es HTML?

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://www.trustedreviews.com/wp-content/uploads/sites/54/2022/10/What-is-HTML.png" alt="HTML">
</div>

**HTML** = **H**yper**T**ext **M**arkup **L**anguage (Lenguaje de Marcado de Hipertexto)

### 🤔 ¿Para qué sirve?
- Es el **esqueleto** de todas las páginas web
- Define la **estructura** y el **contenido**: títulos, párrafos, imágenes, enlaces, etc.
- Es como el **plano** de una casa: dice dónde va cada cosa

### 📋 Características básicas
- ✅ Usa **etiquetas** (tags) para definir elementos: `<etiqueta>contenido</etiqueta>`
- ✅ Las etiquetas tienen **apertura** y **cierre** (la mayoría)
- ✅ Se puede **anidar** etiquetas unas dentro de otras
- ✅ Los navegadores lo interpretan y muestran visualmente

---

## 🎨 ¿Qué es CSS?

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://www.oxfordwebstudio.com/user/pages/06.da-li-znate/sta-je-css/sta-je-css.png" alt="CSS">
</div>

**CSS** = **C**ascading **S**tyle **S**heets (Hojas de Estilo en Cascada)

### 🤔 ¿Para qué sirve?
- Es la **vestimenta** de tu página web
- Define **colores, tamaños, fuentes, espacios, posiciones**
- Convierte el esqueleto HTML en algo **visualmente atractivo**

### 💡 Analogía
- **HTML** = La estructura de una casa (paredes, puertas, ventanas)
- **CSS** = La decoración (pintura, muebles, cortinas)
- **JavaScript** = La funcionalidad (luz eléctrica, agua, puertas automáticas) ← Próxima clase

---

## 💻 Preparación del entorno (10 min)

### 🎯 Lo que necesitas
- ✅ Un editor de texto (VS Code - ya lo usaste en backend)
- ✅ Un navegador web (Chrome, Firefox, Edge)
- ✅ ¡Eso es todo! No necesitas instalar nada más

### 📁 Crear la estructura del proyecto

1. **Abre tu repositorio en VS Code:**
   - File → Open Folder
   - Selecciona tu repositorio `curso-backend-fumc`

2. **Crea una carpeta para el frontend:**
   ```bash
   mkdir clase1-mi-primera-web
   cd clase1-mi-primera-web
   ```

3. **Crea tu primer archivo HTML:**
   - Right-click en la carpeta `clase1-mi-primera-web` → New File
   - Nómbralo: `index.html`

---

## 🏗️ Tu primera página HTML

### Paso 1: Estructura básica de HTML

Copia este código en tu archivo `index.html`:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página Web</title>
</head>
<body>
    <h1>¡Hola Mundo!</h1>
    <p>Esta es mi primera página web</p>
</body>
</html>
```

### 🔍 Explicación línea por línea

```html
<!DOCTYPE html>  <!-- Le dice al navegador que esto es HTML5 -->
<html lang="es"> <!-- Inicia el documento HTML, en español -->
<head>           <!-- Información sobre la página (no se ve) -->
    <meta charset="UTF-8">  <!-- Permite usar acentos y ñ -->
    <title>Mi Primera Página Web</title>  <!-- Título de la pestaña -->
</head>
<body>           <!-- Contenido visible de la página -->
    <h1>¡Hola Mundo!</h1>  <!-- Encabezado principal -->
    <p>Esta es mi primera página web</p>  <!-- Párrafo -->
</body>
</html>          <!-- Cierra el documento -->
```

### 👀 Ver tu página en el navegador

**Opción 1: Doble clic**
- Ve a la carpeta donde está `index.html`
- Doble clic en el archivo → Se abre en tu navegador

**Opción 2: Desde VS Code**
- Right-click en `index.html` → "Open with Live Server" (si tienes la extensión)
- O arrastra el archivo al navegador

**✅ Verificación:** Deberías ver "¡Hola Mundo!" en grande y un párrafo debajo.

---

## 📝 Etiquetas HTML más comunes

### Títulos (Headings)
```html
<h1>Título principal - El más grande</h1>
<h2>Título secundario</h2>
<h3>Título terciario</h3>
<h4>Título nivel 4</h4>
<h5>Título nivel 5</h5>
<h6>Título nivel 6 - El más pequeño</h6>
```

### Párrafos y texto
```html
<p>Este es un párrafo normal.</p>
<p>Este es <strong>texto en negrita</strong> (importante).</p>
<p>Este es <em>texto en cursiva</em> (énfasis).</p>
<p>Este es <u>texto subrayado</u>.</p>
<br> <!-- Salto de línea -->
```

### Listas
```html
<!-- Lista desordenada (con viñetas) -->
<ul>
    <li>Elemento 1</li>
    <li>Elemento 2</li>
    <li>Elemento 3</li>
</ul>

<!-- Lista ordenada (con números) -->
<ol>
    <li>Primer paso</li>
    <li>Segundo paso</li>
    <li>Tercer paso</li>
</ol>
```

### Enlaces e imágenes
```html
<!-- Enlace -->
<a href="https://www.google.com">Ir a Google</a>

<!-- Imagen -->
<img src="https://via.placeholder.com/300" alt="Imagen de ejemplo">
```

### Contenedores
```html
<!-- Div: contenedor genérico (bloque) -->
<div>
    <p>Contenido dentro de un div</p>
</div>

<!-- Span: contenedor en línea -->
<p>Este texto tiene <span>una parte especial</span> dentro.</p>
```

---

## 🎨 Agregando estilos con CSS

### Método 1: CSS Interno (para empezar)

Modifica tu `index.html` para que quede así:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página Web</title>
    
    <!-- AQUÍ AGREGAMOS LOS ESTILOS CSS -->
    <style>
        /* Estilos para el body (toda la página) */
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 20px;
        }
        
        /* Estilos para el h1 */
        h1 {
            color: #2c3e50;
            text-align: center;
        }
        
        /* Estilos para los párrafos */
        p {
            color: #555;
            font-size: 18px;
            line-height: 1.6;
        }
    </style>
</head>
<body>
    <h1>¡Hola Mundo!</h1>
    <p>Esta es mi primera página web con estilos CSS</p>
</body>
</html>
```

**👀 Recarga el navegador** (F5) y observa los cambios.

### 🎨 Propiedades CSS más usadas

```css
/* Colores */
color: blue;              /* Color del texto */
background-color: yellow; /* Color de fondo */

/* Texto */
font-size: 20px;         /* Tamaño de letra */
font-family: Arial;      /* Tipo de letra */
font-weight: bold;       /* Grosor (negrita) */
text-align: center;      /* Alineación */

/* Espaciado */
margin: 10px;            /* Espacio exterior */
padding: 15px;           /* Espacio interior */

/* Bordes */
border: 2px solid black; /* Borde */
border-radius: 10px;     /* Bordes redondeados */

/* Tamaño */
width: 300px;            /* Ancho */
height: 200px;           /* Alto */
```

---

## 🛠️ Actividad práctica 1: Tarjeta de presentación (30 min)

### 🎯 Objetivo
Crear una página web con tu información personal, usando HTML y CSS.

### Paso 1: Estructura HTML

Reemplaza el contenido de `<body>` en tu `index.html`:

```html
<body>
    <div class="container">
        <h1>Mi Tarjeta de Presentación</h1>
        
        <div class="card">
            <img src="https://via.placeholder.com/150" alt="Mi foto">
            <h2>Tu Nombre Completo</h2>
            <p class="subtitle">Estudiante de Desarrollo Web</p>
            
            <div class="info">
                <h3>Sobre mí</h3>
                <p>Escribe algo sobre ti, tus intereses en tecnología, etc.</p>
            </div>
            
            <div class="info">
                <h3>Habilidades</h3>
                <ul>
                    <li>HTML</li>
                    <li>CSS</li>
                    <li>FastAPI (Backend)</li>
                </ul>
            </div>
            
            <div class="info">
                <h3>Contacto</h3>
                <p>Email: tu@email.com</p>
                <p>GitHub: <a href="https://github.com/tu-usuario">@tu-usuario</a></p>
            </div>
        </div>
    </div>
</body>
```

### Paso 2: Estilos CSS

Reemplaza el contenido de `<style>` en el `<head>`:

```html
<style>
    /* Reset básico */
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    
    /* Estilos del body */
    body {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px;
    }
    
    /* Contenedor principal */
    .container {
        width: 100%;
        max-width: 600px;
    }
    
    /* Título principal */
    h1 {
        color: white;
        text-align: center;
        margin-bottom: 30px;
        font-size: 32px;
        text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
    }
    
    /* Tarjeta */
    .card {
        background-color: white;
        border-radius: 20px;
        padding: 40px;
        box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        text-align: center;
    }
    
    /* Imagen */
    .card img {
        width: 150px;
        height: 150px;
        border-radius: 50%;
        border: 5px solid #667eea;
        margin-bottom: 20px;
    }
    
    /* Nombre */
    .card h2 {
        color: #2c3e50;
        font-size: 28px;
        margin-bottom: 10px;
    }
    
    /* Subtítulo */
    .subtitle {
        color: #7f8c8d;
        font-size: 16px;
        margin-bottom: 30px;
    }
    
    /* Secciones de información */
    .info {
        text-align: left;
        margin-bottom: 25px;
        padding: 20px;
        background-color: #f8f9fa;
        border-radius: 10px;
    }
    
    .info h3 {
        color: #667eea;
        margin-bottom: 10px;
        font-size: 20px;
    }
    
    .info p {
        color: #555;
        line-height: 1.6;
        margin-bottom: 8px;
    }
    
    /* Listas */
    .info ul {
        list-style: none;
        padding-left: 0;
    }
    
    .info li {
        color: #555;
        padding: 8px 0;
        padding-left: 20px;
        position: relative;
    }
    
    .info li:before {
        content: "✓";
        color: #667eea;
        font-weight: bold;
        position: absolute;
        left: 0;
    }
    
    /* Enlaces */
    a {
        color: #667eea;
        text-decoration: none;
        font-weight: bold;
    }
    
    a:hover {
        color: #764ba2;
        text-decoration: underline;
    }
</style>
```

### Paso 3: Personalizar

1. **Cambia el nombre** por el tuyo
2. **Escribe sobre ti** en la sección "Sobre mí"
3. **Agrega tus habilidades** (pueden ser las que estás aprendiendo)
4. **Actualiza el email y GitHub** con tus datos

### 👀 Ver los cambios
- Guarda el archivo (`Ctrl + S`)
- Recarga el navegador (`F5`)
- ¡Deberías ver una tarjeta profesional con degradado morado!

---

## 🎨 Actividad práctica 2: Experimentando con estilos (20 min)

### 🎯 Retos para practicar

Intenta hacer estos cambios y observa qué pasa:

#### Reto 1: Cambiar colores
```css
/* Cambia el degradado del fondo */
background: linear-gradient(135deg, #ff6b6b 0%, #feca57 100%);

/* Cambia el color del borde de la imagen */
border: 5px solid #ff6b6b;

/* Cambia el color de los títulos h3 */
color: #ff6b6b;
```

#### Reto 2: Cambiar tamaños
```css
/* Haz el texto más grande */
font-size: 20px;

/* Haz la imagen más pequeña */
width: 100px;
height: 100px;

/* Agrega más espacio interno a la tarjeta */
padding: 60px;
```

#### Reto 3: Agregar efectos
```css
/* Sombra al pasar el mouse sobre la tarjeta */
.card:hover {
    transform: scale(1.05);
    transition: all 0.3s ease;
}

/* Subrayado animado en enlaces */
a {
    transition: all 0.3s ease;
}
```

### 💡 Consejo
Cada vez que hagas un cambio:
1. **Guarda** el archivo (`Ctrl + S`)
2. **Recarga** el navegador (`F5`)
3. **Observa** qué cambió

¡Así aprendes experimentando!

---

## 📊 Estructura de un proyecto web

### 📁 Organización recomendada
```
clase1-mi-primera-web/
│
├── index.html          (Página principal)
├── css/
│   └── styles.css      (Estilos externos - próxima clase)
├── js/
│   └── script.js       (JavaScript - próxima clase)
└── img/
    └── foto.jpg        (Imágenes)
```

Por ahora, tenemos todo en un solo archivo `index.html` para simplificar.

---

## 🎯 Entregable de la clase

### Checklist de lo que debes tener:

✅ **Archivo `index.html` con:**
- Estructura HTML básica completa
- Tarjeta de presentación personalizada con tu información
- Estilos CSS aplicados

✅ **Personalización:**
- Tu nombre real
- Descripción personal auténtica
- Tus habilidades actuales
- Enlace a tu GitHub real

✅ **Subir a GitHub:**
```bash
git add .
git commit -m "Clase 1: Mi primera página web con HTML y CSS"
git push
```

### 📤 Entrega
- **Sube tu código** a tu repositorio de GitHub
- **Comparte el link** de tu repositorio
- **Opcional:** Despliega tu página con GitHub Pages (te enseñaremos después)

---

## 🎨 Galería de colores útiles

### Paletas de colores populares

**Paleta 1: Azul moderno**
```css
#3498db  /* Azul principal */
#2980b9  /* Azul oscuro */
#ecf0f1  /* Gris claro */
#2c3e50  /* Gris oscuro */
```

**Paleta 2: Verde natural**
```css
#27ae60  /* Verde */
#16a085  /* Verde azulado */
#f39c12  /* Naranja */
#e74c3c  /* Rojo */
```

**Paleta 3: Morado vibrante**
```css
#9b59b6  /* Morado */
#8e44ad  /* Morado oscuro */
#3498db  /* Azul */
#1abc9c  /* Turquesa */
```

**Paleta 4: Rojo energético**
```css
#e74c3c  /* Rojo */
#c0392b  /* Rojo oscuro */
#34495e  /* Gris azulado */
#95a5a6  /* Gris */
```

### 🌈 Recursos de colores
- **Coolors:** https://coolors.co/ (generador de paletas)
- **Adobe Color:** https://color.adobe.com/
- **Flat UI Colors:** https://flatuicolors.com/

---

## 🔍 Recursos adicionales

### 📚 Documentación
- **MDN Web Docs (HTML):** https://developer.mozilla.org/es/docs/Web/HTML
- **MDN Web Docs (CSS):** https://developer.mozilla.org/es/docs/Web/CSS
- **W3Schools:** https://www.w3schools.com/

### 🎨 Inspiración de diseño
- **Dribbble:** https://dribbble.com/
- **Behance:** https://www.behance.net/
- **Awwwards:** https://www.awwwards.com/

### 🛠️ Herramientas útiles
- **Can I Use:** https://caniuse.com/ (compatibilidad de navegadores)
- **CSS Gradient:** https://cssgradient.io/ (generador de degradados)
- **Google Fonts:** https://fonts.google.com/ (fuentes gratuitas)

---

## 📝 Resumen de la clase

### ✅ Lo que aprendimos hoy:

1. **HTML básico:**
   - Estructura de un documento HTML
   - Etiquetas principales: `<h1>`, `<p>`, `<div>`, `<ul>`, `<li>`, `<a>`, `<img>`
   - Cómo anidar elementos

2. **CSS básico:**
   - Qué es CSS y para qué sirve
   - Selectores básicos (etiquetas, clases)
   - Propiedades de color, texto, espaciado, bordes
   - Gradientes y efectos visuales

3. **Flujo de trabajo:**
   - Editar código → Guardar → Recargar navegador
   - Ver cambios en tiempo real
   - Experimentar sin miedo

### 🎯 Próxima clase:
- JavaScript: hacer la página **interactiva**
- Eventos: clicks, formularios, validaciones
- Preparación para conectar con el backend (APIs)

---

## 💡 Consejos finales

### Para practicar en casa:
1. **Experimenta con los colores** de tu tarjeta
2. **Agrega más secciones** (hobbies, proyectos, etc.)
3. **Cambia las fuentes** de Google Fonts
4. **Intenta replicar** una página web simple que te guste

### Si algo no funciona:
1. **Verifica que guardaste** el archivo (`Ctrl + S`)
2. **Recarga el navegador** (`F5` o `Ctrl + F5`)
3. **Revisa la consola** del navegador (`F12` → Console)
4. **Compara tu código** con los ejemplos de la clase

### Recuerda:
- ✅ **Todos los programadores comienzan aquí** - es normal no entender todo al principio
- ✅ **La práctica hace al maestro** - mientras más experimentes, más aprenderás
- ✅ **No tengas miedo de romper cosas** - siempre puedes deshacer cambios con Git
- ✅ **Pregunta todo lo que no entiendas** - para eso estamos

---

**¡Felicidades!** 🎉 Has creado tu primera página web. En la próxima clase la haremos interactiva con JavaScript.

---

**Última actualización:** Octubre 2025  
**Versión:** 1.0
