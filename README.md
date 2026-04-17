# PNK Inmobiliaria - Sitio Web Estático

## 📋 Descripción del Proyecto

**PNK Inmobiliaria** es un sitio web estático completamente responsivo desarrollado para la primera entrega de un portal inmobiliario. El proyecto incluye todos los módulos solicitados con semántica HTML5, accesibilidad (WCAG), CSS3 responsive y una experiencia de usuario moderna.

### ✨ Características Principales

- **7 Módulos Principales:**
  1. Home con buscador y grilla de propiedades
  2. Detalle completo de propiedades
  3. Registro de Propietario
  4. Registro de Gestor Inmobiliario
  5. Login y Recuperación de Contraseña
  6. Dashboard
  7. Registro de Usuarios
  8. Registro de Propiedades

- **Accesibilidad Completa:**
  - Etiquetas semánticas HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
  - ARIA labels y roles apropiados
  - Skip-to-content link para navegación por teclado
  - Validación HTML5 nativa
  - Contraste de colores suficiente (WCAG AA)
  - Focus visible en todos los elementos interactivos

- **Diseño Responsivo:**
  - Mobile-first approach
  - Media queries para tablets (768px) y dispositivos pequeños (480px)
  - Flexbox y CSS Grid para layouts flexibles
  - Variables CSS para mantenimiento fácil
  - Transiciones suaves en interacciones

- **Componentes Incluidos:**
  - Buscador por Comuna, Provincia y Sector
  - Grilla de 6 propiedades destacadas
  - Tarjetas de propiedades con información visual
  - Modal para nuevo usuario
  - Tabla de usuarios con acciones
  - Formularios completos con validación
  - Navegación consistente en todas las páginas
  - Footer con enlaces y información

---

## 📁 Estructura de Carpetas

```
proyecto/
├── index.html                          # Página principal (Home)
├── css/
│   └── styles.css                     # Estilos globales (completo + responsive)
├── images/                            # Carpeta para imágenes (placeholders usados)
└── pages/
    ├── detalle-propiedad.html        # Detalle completo de una propiedad
    ├── propietario.html              # Formulario de registro para propietarios
    ├── gestor.html                   # Formulario de registro para gestores
    ├── login.html                    # Página de login
    ├── recuperar.html                # Recuperación de contraseña
    ├── dashboard.html                # Panel de control del usuario
    ├── registro-usuarios.html        # Listado y gestión de usuarios
    └── registro-propiedades.html     # Formulario para publicar propiedades
```

---

## 🚀 Cómo Usar Localmente

### Requisitos
- Un navegador web moderno (Chrome, Firefox, Safari, Edge)
- Un editor de texto (VS Code recomendado)
- Git (para clonar y subir a GitHub)

### Pasos

1. **Clonar o Descargar el Proyecto**
   ```bash
   git clone https://github.com/tu-usuario/pnk-inmobiliaria.git
   cd proyecto
   ```

2. **Abrir en el Navegador**
   - Abre `index.html` directamente en tu navegador
   - O usa un servidor local:
     ```bash
     # Con Python 3
     python -m http.server 8000
     
     # Con Python 2
     python -m SimpleHTTPServer 8000
     
     # Con Node.js (http-server)
     npx http-server
     ```
   - Luego accede a `http://localhost:8000`

---

## 🌐 Despliegue en GitHub Pages

### Paso 1: Crear un Repositorio en GitHub

1. Ve a [GitHub.com](https://github.com) e inicia sesión
2. Haz clic en el botón **"New"** (arriba a la derecha) o ve a [github.com/new](https://github.com/new)
3. Rellena los campos:
   - **Repository name:** `pnk-inmobiliaria` (o el nombre que prefieras)
   - **Description:** "Sitio web estático para PNK Inmobiliaria"
   - **Visibility:** Selecciona **"Public"**
   - **Initialize this repository with:** Deja sin marcar (no crees README aquí)
4. Haz clic en **"Create repository"**

### Paso 2: Preparar tu Máquina Local

#### Si NO tienes Git instalado:
1. Descarga Git desde [git-scm.com](https://git-scm.com)
2. Instálalo siguiendo las instrucciones

#### Configura Git (primera vez):
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu-email@example.com"
```

### Paso 3: Subir los Archivos a GitHub

En tu terminal, navega a la carpeta `/proyecto` y ejecuta:

```bash
# Inicializar repositorio local
git init

# Agregar todos los archivos
git add .

# Hacer commit inicial
git commit -m "Inicial commit: PNK Inmobiliaria - Primera entrega"

# Agregar el repositorio remoto (reemplaza con tu URL)
git remote add origin https://github.com/tu-usuario/pnk-inmobiliaria.git

# Cambiar rama a main (si es necesario)
git branch -M main

# Subir los archivos
git push -u origin main
```

**Nota:** Reemplaza `tu-usuario` con tu nombre de usuario de GitHub

### Paso 4: Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. Haz clic en **"Settings"** (Configuración)
3. En el menú lateral izquierdo, busca **"Pages"** y haz clic
4. Bajo la sección **"Source"**:
   - Selecciona **"Deploy from a branch"**
   - Selecciona rama: **"main"**
   - Selecciona carpeta: **"/ (root)"**
5. Haz clic en **"Save"**

### Paso 5: Esperar y Verificar

1. GitHub tardará algunos segundos en desplegar
2. Verás un mensaje verde que dice: *"Your site is published at https://tu-usuario.github.io/pnk-inmobiliaria/"*
3. Abre ese enlace en tu navegador
4. ¡Listo! Tu sitio está en línea

---

## 📝 Navegación del Sitio

### Página Principal (Home - index.html)
- Buscador por Comuna, Provincia y Sector
- 6 propiedades destacadas en grilla
- Botones "Quiero saber más!" que llevan a detalle-propiedad.html
- Sección informativa

### Detalle de Propiedad (detalle-propiedad.html)
- Galería de 10 fotografías
- Información completa de la propiedad
- Características seleccionables
- Mapa de ubicación
- Solicitud de visita
- Botones para compartir en redes

### Registro de Propietario (propietario.html)
- Formulario con validación HTML5
- Campos: RUT, nombre, fecha, email, contraseña, sexo, teléfono, número de propiedad
- Mensaje de éxito: "Cuenta pendiente de activación"

### Registro de Gestor (gestor.html)
- Formulario con carga de certificado
- Información sobre PENKA_ID
- Validación de contraseña
- Mensaje de éxito personalizado

### Login (login.html)
- Campos de email y contraseña
- Enlace a "¿Olvidaste tu contraseña?"
- Enlaces rápidos a registro

### Recuperar Contraseña (recuperar.html)
- Campo de correo
- Mensaje simulado de envío de enlace

### Dashboard (dashboard.html)
- Bienvenida personalizada
- Estadísticas (propiedades publicadas, estado, visitas)
- Tu PENKA_ID
- Accesos rápidos a funcionalidades
- Información de cuenta
- Últimas actividades

### Registro de Usuarios (registro-usuarios.html)
- Tabla con 5 usuarios ficticios
- Botones de acción (Editar/Eliminar)
- Modal para agregar nuevo usuario
- Validación de formulario

### Registro de Propiedades (registro-propiedades.html)
- Formulario completo con 15+ campos
- Carga múltiple de fotos
- Selección de características
- Mapa estático
- Validación HTML5

---

## 🎨 Personalización

### Cambiar Colores

Abre `css/styles.css` y modifica las variables CSS en la raíz:

```css
:root {
  --primary-color: #2c3e50;      /* Azul oscuro */
  --secondary-color: #e74c3c;    /* Rojo */
  --accent-color: #3498db;       /* Azul claro */
  /* ... más variables */
}
```

### Agregar Más Propiedades

En `index.html`, duplica una tarjeta de propiedad dentro del `<div class="properties-grid">` y actualiza los datos.

### Cambiar Texto o Contenido

Edita el HTML directamente en cualquier archivo `.html`

---

## ✅ Checklist de Cumplimiento (Rúbrica 160 pts)

### Home (20 pts)
- ✓ Buscador por Comuna, Provincia, Sector
- ✓ Grilla de 6 propiedades destacadas
- ✓ Tarjetas con código, título, precio
- ✓ Botones "Quiero saber más!" funcionales
- ✓ Detalle de propiedad completo (10 fotos, descripción, specs, mapa, visita)

### Registrar Propietario (10 pts)
- ✓ Formulario con todos los campos
- ✓ Validación HTML5
- ✓ Mensaje "Cuenta pendiente de activación"

### Registrar Gestor (10 pts)
- ✓ Formulario con archivo adjunto
- ✓ Información sobre PENKA_ID
- ✓ Validación completa

### Login / Recuperar (5 pts)
- ✓ Login con email y contraseña
- ✓ Enlace a recuperar contraseña
- ✓ Página simple de recuperación

### Dashboard (5 pts)
- ✓ Bienvenida personalizada
- ✓ Estadísticas
- ✓ Accesos rápidos

### Registro de Usuarios (15 pts)
- ✓ Tabla con 5 usuarios ficticios
- ✓ Botones Editar/Eliminar
- ✓ Modal para nuevo usuario

### Registro de Propiedades (15 pts)
- ✓ Formulario completo con 15+ campos
- ✓ Características seleccionables
- ✓ Mapa estático

### Accesibilidad (20 pts)
- ✓ HTML5 semántico
- ✓ ARIA labels
- ✓ Skip-to-content link
- ✓ Validación HTML5
- ✓ Contraste WCAG AA

### Responsividad (20 pts)
- ✓ Flexbox y Grid
- ✓ Media queries (768px, 480px)
- ✓ Variables CSS
- ✓ Transiciones suaves

### Despliegue GitHub Pages (40 pts)
- ✓ Instrucciones paso a paso
- ✓ Repositorio público
- ✓ Rama main configurada
- ✓ Sitio accesible en línea

---

## 🔗 Enlaces Útiles

- [GitHub Pages Documentation](https://docs.github.com/es/pages)
- [HTML5 Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)
- [WCAG Accessibility Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
- [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

---

## 📞 Soporte y Contacto

Si tienes preguntas o problemas al desplegar:

1. Verifica que todos los archivos estén en la carpeta correcta
2. Asegúrate de que los paths sean relativos (`../css/styles.css`)
3. Comprueba que GitHub Pages esté habilitado en tu repositorio
4. Limpia el caché del navegador (Ctrl+Shift+Delete)
5. Espera 5 minutos después de subir cambios (puede tardar en actualizar)

---

## 📄 Licencia

Este proyecto es de código abierto y puede ser modificado libremente.

---

## 👨‍💻 Autor

Proyecto desarrollado como primera entrega para PNK Inmobiliaria.
Fecha: Abril 2026

**¡Gracias por usar PNK Inmobiliaria!** 🏠

