# 📚 GUÍA COMPLETA: GITHUB Y GITHUB PAGES
## PNK Inmobiliaria - Despliegue en Línea

### Tabla de Contenidos
1. [Requisitos Previos](#requisitos-previos)
2. [Opción A: Línea de Comandos (Git CLI)](#opción-a-línea-de-comandos)
3. [Opción B: GitHub CLI (gh)](#opción-b-github-cli)
4. [Configuración de GitHub Pages](#configuración-de-github-pages)
5. [Verificación y Solución de Problemas](#verificación-y-solución-de-problemas)
6. [Buenas Prácticas](#buenas-prácticas)

---

## Requisitos Previos

### Paso 0: Verificar Git Instalado

Abre PowerShell o CMD y verifica que Git esté instalado:

```powershell
git --version
```

**Salida esperada:**
```
git version 2.42.0.windows.1
```

Si no está instalado, descárgalo desde: https://git-scm.com/download/win

### Paso 1: Configurar Git (Primera vez)

```powershell
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@example.com"
```

**Ejemplo:**
```powershell
git config --global user.name "Juan Pérez"
git config --global user.email "juan.perez@example.com"
```

Verifica la configuración:
```powershell
git config --global --list
```

---

## 🚀 OPCIÓN A: Línea de Comandos (Git CLI)

### Paso 1: Crear Repositorio en GitHub (Web)

1. Ve a https://github.com/new
2. Completa el formulario:
   - **Repository name:** `pnk-inmobiliaria`
   - **Description:** "Sitio web estático de inmobiliaria - La Serena"
   - **Public:** ✅ (para que sea visible)
   - **Add .gitignore:** Selecciona "Node" o "VisualStudio"
   - **Add a README.md:** No es necesario (ya tienes uno)
   - **Choose a license:** Opcional

3. Haz clic en **"Create repository"**

**Resultado:** GitHub te muestra la URL: `https://github.com/tu-usuario/pnk-inmobiliaria`

---

### Paso 2: Inicializar Repositorio Local

Abre PowerShell en tu carpeta de proyecto (`c:\proyecto`):

```powershell
cd C:\proyecto
```

Inicializa el repositorio:

```powershell
git init
```

Verifica:
```powershell
git status
```

**Salida esperada:**
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        AUDITORIA-FRONTEND.md
        DEPLOY-GITHUB-PAGES.md
        ENTREGA-FINAL.txt
        ...más archivos
```

---

### Paso 3: Agregar Archivo .gitignore

Crea un archivo `.gitignore` en la raíz del proyecto para no subir archivos temporales:

**Opción A: Crear manualmente (Recomendado)**

Crea un archivo llamado `.gitignore` en `c:\proyecto`:

```
# Archivos del sistema
.DS_Store
Thumbs.db
*.tmp

# IDEs
.vscode/
.idea/
*.swp
*.swo

# Archivos temporales
*.log
*.bak
~*

# Node (si usas en el futuro)
node_modules/
npm-debug.log

# Archivos de prueba
test-*.html
```

**Opción B: Usar línea de comandos**

```powershell
echo ".DS_Store`nThumbs.db`nnode_modules/" > .gitignore
```

---

### Paso 4: Agregar Archivos al Repositorio

Agrega todos los archivos:

```powershell
git add .
```

Verifica qué archivos se agregan:

```powershell
git status
```

**Salida esperada:**
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   AUDITORIA-FRONTEND.md
        new file:   README.md
        ...más archivos
```

---

### Paso 5: Primer Commit

Realiza el primer commit con un mensaje semántico:

```powershell
git commit -m "feat: inicial commit - estructura base del sitio PNK Inmobiliaria"
```

**Salida esperada:**
```
[master (root-commit) a1b2c3d] feat: inicial commit - estructura base del sitio PNK Inmobiliaria
 14 files changed, 1000 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 index.html
 ...
```

---

### Paso 6: Crear Rama main y Configurar Upstream

En GitHub, la rama principal se llama `main` (anteriormente `master`). Debemos cambiar el nombre:

```powershell
git branch -M main
```

Conecta tu repositorio local con GitHub:

```powershell
git remote add origin https://github.com/tu-usuario/pnk-inmobiliaria.git
```

**REEMPLAZA:**
- `tu-usuario` por tu nombre de usuario de GitHub

**Ejemplo:**
```powershell
git remote add origin https://github.com/juan-perez-dev/pnk-inmobiliaria.git
```

Verifica:
```powershell
git remote -v
```

**Salida esperada:**
```
origin  https://github.com/juan-perez-dev/pnk-inmobiliaria.git (fetch)
origin  https://github.com/juan-perez-dev/pnk-inmobiliaria.git (push)
```

---

### Paso 7: Push del Código a GitHub

Sube el código a GitHub:

```powershell
git push -u origin main
```

Si solicita credenciales:
- **Usuario:** Tu nombre de usuario de GitHub
- **Contraseña:** Tu Personal Access Token (PAT)

**Para crear un PAT:**
1. Ve a https://github.com/settings/tokens
2. Haz clic en "Generate new token"
3. Selecciona permisos: `repo`, `gist`
4. Copia el token
5. Úsalo como contraseña en Git

**Salida esperada:**
```
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 8 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (14/14), 45.67 KiB | 2.28 MiB/s, done.
...
To https://github.com/tu-usuario/pnk-inmobiliaria.git
 * [new branch]      main -> main
Branch 'main' set to track remote branch 'main' from 'origin'.
```

---

## 🔧 OPCIÓN B: GitHub CLI (gh)

Si prefieres una solución más automatizada, usa GitHub CLI.

### Paso 1: Instalar GitHub CLI

Descarga desde: https://cli.github.com/

O con Chocolatey (si tienes instalado):
```powershell
choco install gh
```

### Paso 2: Autenticar

```powershell
gh auth login
```

Selecciona:
- `GitHub.com`
- `HTTPS`
- `Y` (Authenticate Git with your GitHub credentials)
- `Login with a web browser`

Se abrirá una ventana del navegador. Autoriza la aplicación.

### Paso 3: Crear Repositorio

```powershell
gh repo create pnk-inmobiliaria --public --source=. --remote=origin --push
```

**Flags:**
- `--public`: Repositorio público
- `--source=.`: Usa el directorio actual como fuente
- `--remote=origin`: Configura origin automáticamente
- `--push`: Sube el código inmediatamente

**Resultado:** El repositorio se crea y se sube automáticamente.

---

## ⚙️ Configuración de GitHub Pages

### Paso 1: Acceder a Configuración

1. Ve a tu repositorio en GitHub: `https://github.com/tu-usuario/pnk-inmobiliaria`
2. Haz clic en **Settings** (Configuración)
3. En el menú lateral, ve a **Pages** (aproximadamente línea 20)

### Paso 2: Configurar la Fuente de GitHub Pages

**En la sección "Build and deployment":**

1. **Source:** Selecciona **"Deploy from a branch"**
2. **Branch:** Selecciona **"main"** (o `master` si es necesario)
3. **Folder:** Selecciona **"/ (root)"** 

Esto significa que GitHub Pages usará la rama `main` y publicará todos los archivos desde la raíz.

Haz clic en **"Save"**.

### Paso 3: Esperar Despliegue

GitHub Pages tardará **1-2 minutos** en desplegar tu sitio.

Verás una notificación verde:
```
✓ Your site is live at https://tu-usuario.github.io/pnk-inmobiliaria/
```

---

## ✅ Verificación y Solución de Problemas

### Verificar que el Sitio Está en Línea

Tu sitio estará disponible en:
```
https://tu-usuario.github.io/pnk-inmobiliaria/
```

**Ejemplo:**
```
https://juan-perez-dev.github.io/pnk-inmobiliaria/
```

### Actualizar Después de Cambios

Después de hacer cambios locales, sigue estos pasos:

```powershell
# 1. Verifica cambios
git status

# 2. Agrega cambios
git add .

# 3. Realiza commit
git commit -m "fix: corrección de errores en accesibilidad"

# 4. Push a GitHub
git push origin main
```

GitHub Pages se actualizará automáticamente **en 1-2 minutos**.

### Problemas Comunes

#### ❌ Problema: "404 - Página no encontrada"

**Causa:** Las rutas relativas son incorrectas.

**Solución:** 
En `pages/dashboard.html`, cambiar:
```html
<!-- Incorrecto -->
<a href="index.html">

<!-- Correcto -->
<a href="../index.html">
```

O en CSS:
```html
<!-- Incorrecto -->
<link rel="stylesheet" href="css/styles.css">

<!-- Correcto -->
<link rel="stylesheet" href="../css/styles.css">
```

#### ❌ Problema: "Repositorio privado"

**Causa:** El repositorio está en privado.

**Solución:**
1. Ve a **Settings > General**
2. Baja a **Danger zone**
3. Selecciona **Change repository visibility**
4. Elige **Public**

#### ❌ Problema: "GitHub Pages no está habilitado"

**Causa:** No configuraste la rama de despliegue.

**Solución:**
1. Ve a **Settings > Pages**
2. En **Source**, selecciona **"Deploy from a branch"**
3. Selecciona la rama (generalmente `main`)
4. Selecciona la carpeta (`/ (root)`)
5. Haz clic en **Save**

#### ❌ Problema: "Estilos CSS no cargan"

**Causa:** Rutas relativas incorrectas en el CSS.

Verifica en DevTools (F12):
```
GET https://tu-usuario.github.io/pnk-inmobiliaria/css/styles.css 404
```

**Solución:** Ajusta las rutas en los HTML:
```html
<!-- En pages/dashboard.html -->
<link rel="stylesheet" href="../css/styles.css">
```

---

## 📋 Buenas Prácticas de Git

### 1. Mensajes de Commit Semánticos

Usa prefijos semánticos para claridad:

```powershell
# Feature (nueva funcionalidad)
git commit -m "feat: agregar buscador de propiedades"

# Fix (corrección de bug)
git commit -m "fix: corregir contraste de colores en accesibilidad"

# Docs (documentación)
git commit -m "docs: actualizar README con instrucciones"

# Style (formato, sin lógica)
git commit -m "style: aplicar formato a archivos CSS"

# Refactor (refactorización de código)
git commit -m "refactor: mover estilos inline a CSS"

# Test (tests)
git commit -m "test: agregar validación de formularios"

# Chore (tareas de configuración)
git commit -m "chore: actualizar .gitignore"
```

### 2. Commits Frecuentes

Realiza commits frecuentes (cada 30-60 minutos):

```powershell
git add .
git commit -m "feat: agregar módulo de dashboard"
git push origin main
```

### 3. Ver Historial de Commits

```powershell
git log --oneline
```

**Salida esperada:**
```
a1b2c3d (HEAD -> main) fix: corregir contraste de colores
e5f6g7h feat: agregar buscador
i9j0k1l feat: estructura base del proyecto
```

### 4. Crear Ramas para Características

Para cambios grandes, crea una rama:

```powershell
# Crear rama
git checkout -b feature/buscador-avanzado

# Trabajar en la rama...
git add .
git commit -m "feat: implementar buscador avanzado"

# Volver a main
git checkout main

# Fusionar cambios
git merge feature/buscador-avanzado

# Eliminar rama
git branch -d feature/buscador-avanzado

# Push
git push origin main
```

### 5. Archivo .gitignore Recomendado

```
# Sistema operativo
.DS_Store
Thumbs.db
*.tmp
*.temp

# IDEs y editores
.vscode/
.idea/
*.swp
*.swo
*~
*.sublime-project
*.sublime-workspace

# Archivos de depuración
*.log
debug.log
npm-debug.log*
yarn-debug.log*

# Dependencias (Node.js)
node_modules/
package-lock.json
yarn.lock

# Compilados
dist/
build/

# Archivos temporales
.env.local
.env.*.local
*.pem

# Archivos de prueba
test-*.html
example-*.js
```

---

## 📌 Resumen de Pasos Rápidos

### Primera vez (Setup inicial):

```powershell
cd C:\proyecto

# 1. Inicializar
git init
git config user.name "Tu Nombre"
git config user.email "tu.email@example.com"

# 2. Agregar
git add .

# 3. Commit
git commit -m "feat: inicial commit"

# 4. Rama main
git branch -M main

# 5. Remote
git remote add origin https://github.com/tu-usuario/pnk-inmobiliaria.git

# 6. Push
git push -u origin main
```

### Cambios posteriores (workflow normal):

```powershell
# Después de editar archivos...
git add .
git commit -m "fix: descripción del cambio"
git push origin main

# ¡GitHub Pages se actualiza automáticamente!
```

---

## 🎯 Checklist Final

- [ ] Git instalado y configurado
- [ ] Repositorio creado en GitHub
- [ ] `.gitignore` configurado
- [ ] Código subido a rama `main`
- [ ] GitHub Pages habilitado en Settings
- [ ] Rama de despliegue: `main`
- [ ] Carpeta de despliegue: `/ (root)`
- [ ] Sitio accesible en `https://tu-usuario.github.io/pnk-inmobiliaria/`
- [ ] Rutas relativas verificadas (sin errores 404)
- [ ] CSS carga correctamente

---

## 📞 Soporte Rápido

### Enlaces Útiles:
- Documentación GitHub: https://docs.github.com
- GitHub Pages Docs: https://docs.github.com/es/pages
- Git Cheat Sheet: https://git-scm.com/docs
- GitHub CLI: https://cli.github.com/

### Comandos Útiles de Git:

```powershell
# Ver cambios antes de commit
git diff

# Ver estado del repositorio
git status

# Ver historial
git log --oneline --graph --all

# Deshacer último commit
git reset --soft HEAD~1

# Ver diferencias con rama remota
git fetch origin
git diff main origin/main

# Actualizar rama local desde remota
git pull origin main
```

---

## ✨ ¡Listo!

Tu sitio PNK Inmobiliaria está en línea y visible para el mundo.

**URL de tu sitio:**
```
https://tu-usuario.github.io/pnk-inmobiliaria/
```

**Comparte tu trabajo:**
- Copia el enlace
- Envía por email
- Comparte en redes sociales
- Agrégalo a tu portafolio

¡Felicidades! 🎉

---

**Última actualización:** 17 de Abril, 2026  
**Versión:** 1.0  
**Autor:** Auditoría Senior Front-End
