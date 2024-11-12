
# Ejercicio de Workflows Diversos con GitHub Actions - DAW1211

## Objetivo

En este ejercicio, cada equipo practicará la creación y configuración de un workflow distinto en GitHub Actions para implementar flujos de CI/CD personalizados. Cada equipo configurará un workflow en el archivo `ci.yml` en función de las instrucciones específicas proporcionadas a continuación.

## Instrucciones Generales

1. Este ejercicio utilizará los archivos ya presentes en la rama `main` del repositorio `DAW1211` (`index.html`, `styles.css`, `script.js`).
2. Cada equipo deberá configurar un workflow único que se ejecute en cada `push` y en las `pull requests` en la rama `main`.

---

## Instrucciones para cada Equipo

### Equipo 1: Workflow para Validación de HTML

1. Crear una rama llamada `workflow-equipo1`.
   ```bash
   git checkout -b workflow-equipo1
   ```

2. Crear una carpeta `.github/workflows` en esta rama y dentro de ella un archivo `ci.yml`.

3. Configurar el workflow para validar la sintaxis de `index.html` usando una acción de validación de HTML.

   Ejemplo de configuración de `ci.yml`:
   ```yaml
   name: HTML Validation

   on:
     push:
       branches: [ main ]
     pull_request:
       branches: [ main ]

   jobs:
     validate-html:
       runs-on: ubuntu-latest

       steps:
         - name: Check out the repository
           uses: actions/checkout@v2

         - name: Validate HTML
           uses: chrislennon/action-html-validate@v1
           with:
             files: index.html
   ```

4. Hacer commit y push de los cambios:
   ```bash
   git add .github/workflows/ci.yml
   git commit -m "Agregar workflow de validación de HTML"
   git push origin workflow-equipo1
   ```

5. Crear una Pull Request para que otros miembros del equipo revisen y aprueben.

---

### Equipo 2: Workflow para Linter de CSS

1. Crear una rama llamada `workflow-equipo2`.
   ```bash
   git checkout -b workflow-equipo2
   ```

2. Crear la carpeta `.github/workflows` y dentro de ella el archivo `ci.yml`.

3. Configurar el workflow para revisar el archivo `styles.css` utilizando `stylelint` para detectar errores de sintaxis.

   Ejemplo de configuración de `ci.yml`:
   ```yaml
   name: CSS Linting

   on:
     push:
       branches: [ main ]
     pull_request:
       branches: [ main ]

   jobs:
     lint-css:
       runs-on: ubuntu-latest

       steps:
         - name: Check out the repository
           uses: actions/checkout@v2

         - name: Lint CSS
           run: |
             npm install -g stylelint
             stylelint "styles.css"
   ```

4. Hacer commit y push de los cambios:
   ```bash
   git add .github/workflows/ci.yml
   git commit -m "Agregar workflow de linter de CSS"
   git push origin workflow-equipo2
   ```

5. Crear una Pull Request para revisión y aprobación.

---

### Equipo 3: Workflow para Pruebas de JavaScript

1. Crear una rama llamada `workflow-equipo3`.
   ```bash
   git checkout -b workflow-equipo3
   ```

2. Crear la carpeta `.github/workflows` y dentro de ella el archivo `ci.yml`.

3. Configurar el workflow para ejecutar pruebas en el archivo `script.js`.

   Ejemplo de configuración de `ci.yml`:
   ```yaml
   name: JavaScript Testing

   on:
     push:
       branches: [ main ]
     pull_request:
       branches: [ main ]

   jobs:
     test-js:
       runs-on: ubuntu-latest

       steps:
         - name: Check out the repository
           uses: actions/checkout@v2

         - name: Run JavaScript Tests
           run: |
             echo "Running JavaScript tests..."
             node script.js
   ```

4. Hacer commit y push de los cambios:
   ```bash
   git add .github/workflows/ci.yml
   git commit -m "Agregar workflow de pruebas de JavaScript"
   git push origin workflow-equipo3
   ```

5. Crear una Pull Request para que otros miembros del equipo revisen y aprueben.

---

## Resultados Esperados

Al finalizar el ejercicio, el repositorio `DAW1211` debe tener tres workflows distintos configurados para HTML, CSS y JavaScript, ejecutándose en cada push o pull request hacia `main`.
