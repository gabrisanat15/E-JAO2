# Página del póster científico

Página web de un solo archivo (`index.html`) pensada para enlazarse desde un
código QR en un póster científico: visor molecular interactivo, vídeo de
dinámica molecular, datos y contacto.

## Estructura del proyecto

```
.
├── index.html        ← la página (todo el contenido se edita en CONFIG, al
│                        principio del <script> al final del archivo)
├── vercel.json        ← cabeceras para servir bien el vídeo y el .pdb
├── assets/
│   ├── dimero.pdb     ← sustituye por tu archivo real
│   └── dinamica.mp4   ← sustituye por tu archivo real
└── .gitignore
```

## 1. Personalizar

Abre `index.html`, busca el bloque `const CONFIG = { ... }` y rellena:
título, residuos a resaltar, datos de la dinámica y tus datos de contacto.
Las instrucciones detalladas están en los comentarios justo encima.

Sustituye `assets/dimero.pdb` y `assets/dinamica.mp4` por tus archivos reales
(manteniendo esos mismos nombres, o cambiando las rutas en CONFIG si usas
otros nombres).

## 2. Subir a GitHub

```bash
git init
git add .
git commit -m "Página del póster"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/TU-REPOSITORIO.git
git push -u origin main
```

(Antes crea el repositorio vacío en github.com → "New repository".)

> Si `dinamica.mp4` pesa más de ~50 MB, GitHub puede rechazar el push.
> En ese caso, aloja el vídeo aparte (por ejemplo en otro repo, usando su
> URL "raw") y pega esa URL completa en `videoUrl` dentro de CONFIG en
> lugar de la ruta relativa.

## 3. Desplegar en Vercel

1. Entra en [vercel.com](https://vercel.com) e inicia sesión con tu cuenta
   de GitHub.
2. "Add New…" → "Project" → selecciona tu repositorio.
3. Framework Preset: déjalo en **Other** (no hace falta build command ni
   output directory, es un sitio estático).
4. Pulsa **Deploy**.
5. En un minuto tendrás una URL pública del tipo
   `https://tu-proyecto.vercel.app`.

Cada vez que hagas `git push`, Vercel vuelve a desplegar automáticamente.

## 4. Generar el código QR

Genera un QR que apunte a la URL de Vercel (con cualquier generador de QR
gratuito) y colócalo en tu póster.
