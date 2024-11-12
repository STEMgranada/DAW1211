
# Ejercicio Colaborativo en Git - DAW1211

## Objetivo

En este ejercicio, los equipos practicarán la gestión colaborativa de un repositorio de Git, aplicando comandos avanzados para manejar ramas, realizar merges, rebases, y manejar conflictos. Cada equipo estará compuesto por 4 personas y deberá seguir los pasos detallados a continuación para lograr una integración completa de su trabajo en el repositorio.

## Instrucciones Generales

1. Cada equipo trabajará en su propio directorio dentro del repositorio `DAW1211`.
2. El proyecto constará de un archivo HTML (`index.html`), un archivo CSS (`styles.css`), y un archivo JavaScript (`script.js`).
3. La práctica se estructura para que cada miembro de cada equipo cree una sección y luego los integrantes se encarguen de integrar sus secciones en un solo proyecto.

---

## Pasos Detallados

### Paso 1: Clonar el Repositorio


### Paso 2: Crear una Rama por Persona

Cada miembro creará una rama para trabajar en su sección del proyecto. Nombrar las ramas con el prefijo `equipoX-nombre`, donde `X` representa el número del equipo (1, 2 o 3), y `nombre` es el nombre del miembro.

Ejemplo:
```bash
git checkout -b equipo1-ana
```

### Paso 3: Crear Archivos Iniciales

1. Cada miembro creará el archivo `index.html`, `styles.css` o `script.js` en su rama con un contenido inicial.
   
   - Ejemplo de `index.html`:
     ```html
     <!DOCTYPE html>
     <html lang="es">
     <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width, initial-scale=1.0">
         <title>Proyecto Colaborativo</title>
         <link rel="stylesheet" href="styles.css">
     </head>
     <body>
         <h1>Bienvenidos al Proyecto Colaborativo</h1>
         <script src="script.js"></script>
     </body>
     </html>
     ```

   - Ejemplo de `styles.css`:
     ```css
     body {
         font-family: Arial, sans-serif;
         background-color: #f4f4f9;
         text-align: center;
     }
     h1 {
         color: #333;
     }
     ```

   - Ejemplo de `script.js`:
     ```javascript
     document.addEventListener("DOMContentLoaded", function() {
         console.log("Proyecto Colaborativo - JavaScript activo");
     });
     ```

### Paso 4: Commit Inicial

Cada miembro debe realizar un commit inicial con el contenido que ha añadido.
```bash
git add .
git commit -m "Commit inicial de <nombre>"
```

### Paso 5: Subir la Rama al Repositorio

Subir las ramas creadas al repositorio remoto:
```bash
git push origin equipoX-nombre
```

### Paso 6: Integración en una Rama Común

1. Una vez que cada miembro haya completado su sección, crear una rama de integración llamada `integracion-equipoX`.
   ```bash
   git checkout main
   git pull origin main
   git checkout -b integracion-equipoX
   ```

2. Cada miembro debe fusionar su rama en `integracion-equipoX`.
   ```bash
   git merge equipoX-nombre
   ```

3. Resolver cualquier conflicto que pueda surgir y realizar un commit tras resolver los conflictos:
   ```bash
   git add .
   git commit -m "Conflictos resueltos para integración"
   ```

### Paso 7: Crear un Pull Request

1. Subir la rama `integracion-equipoX` al repositorio remoto.
   ```bash
   git push origin integracion-equipoX
   ```

2. Crear un Pull Request desde `integracion-equipoX` hacia `main` y asignar a los otros miembros del equipo como revisores para que aprueben la integración.

### Paso 8: Revisión y Fusión Final

1. Los miembros del equipo revisarán y aprobarán la Pull Request.
2. Una vez aprobada, fusionar la Pull Request en `main`.

### Paso 9: Actualización Local

Cada miembro debe actualizar su copia local de `main`:
```bash
git checkout main
git pull origin main
```

---

## Resultados Esperados

Al finalizar el ejercicio, el repositorio `DAW1211` debe contener una versión final integrada del proyecto con los cambios de cada miembro del equipo en la rama `main`.

