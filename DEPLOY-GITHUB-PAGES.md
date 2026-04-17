# GUÍA RÁPIDA DE DESPLIEGUE - PNK INMOBILIARIA

## ⚡ COMANDOS GIT PASO A PASO (Copia y Pega)

### OPCIÓN 1: Primer tiempo (repositorio nuevo)

```bash
# 1. Navega a tu carpeta proyecto
cd C:\ruta\a\tu\proyecto

# 2. Inicializa Git
git init

# 3. Configura tu usuario (solo primera vez)
git config user.name "Tu Nombre Aquí"
git config user.email "tu-email@example.com"

# 4. Agrega todos los archivos
git add .

# 5. Hace el primer commit
git commit -m "Inicial: PNK Inmobiliaria - Primera entrega"

# 6. Renombra la rama a 'main' si es necesario
git branch -M main

# 7. Conecta con tu repositorio de GitHub
# (Reemplaza: tu-usuario con tu nombre de usuario de GitHub)
git remote add origin https://github.com/tu-usuario/pnk-inmobiliaria.git

# 8. Sube los archivos
git push -u origin main
```

---

### OPCIÓN 2: Después de cambios (actualizaciones)

```bash
# Si hiciste cambios, simplemente:
git add .
git commit -m "Descripción del cambio"
git push
```

---

## 🔧 SOLUCIÓN DE PROBLEMAS COMUNES

### Error: "fatal: not a git repository"
**Solución:** Ejecuta `git init` en la carpeta proyecto

### Error: "remote already exists"
**Solución:** Ejecuta primero `git remote remove origin` luego agrega nuevamente

### Los cambios no aparecen en GitHub Pages
**Solución:** 
1. Espera 5-10 minutos
2. Limpia caché: Ctrl+Shift+Delete
3. Verifica que GitHub Pages esté habilitado en Settings > Pages

### Error de autenticación
**Solución:**
1. Genera un token personal en GitHub: https://github.com/settings/tokens
2. Usa el token como contraseña

---

## 📊 VER ESTADO DEL REPOSITORIO

```bash
# Ver estado actual
git status

# Ver commits
git log

# Ver cambios no guardados
git diff

# Ver ramas
git branch -a
```

---

## 🌐 TU SITIO EN VIVO

Después de hacer `git push`, accede a:

**https://tu-usuario.github.io/pnk-inmobiliaria/**

(Reemplaza "tu-usuario" con tu nombre de usuario de GitHub)

---

## 📱 VERIFICAR QUE TODO FUNCIONE

1. ✓ Navega por todas las páginas desde el menú
2. ✓ Prueba los botones "Quiero saber más!"
3. ✓ Prueba los formularios
4. ✓ Verifica que sea responsive (F12 → responsive design mode)
5. ✓ Comprueba accesibilidad (F12 → Lighthouse)

---

## 💡 TIPS

- Guarda tu URL en favoritos para fácil acceso
- Comparte el enlace con tu profesor/equipo
- Puedes hacer cambios locales y hacer `git push` para actualizar
- GitHub Pages se actualiza automáticamente cada vez que hagas push

---

¡Listo! Tu sitio está en GitHub Pages 🚀

