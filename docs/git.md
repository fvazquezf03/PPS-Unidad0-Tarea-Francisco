# Documentación del proceso con Git

## Creación del repositorio

# 🚀 Crear y subir un repositorio a GitHub desde Git (todo en uno)

```sh
# 1️⃣ Crear una carpeta para el proyecto y moverse a ella
mkdir mi-proyecto
cd mi-proyecto

# 2️⃣ Inicializar Git
git init

# 3️⃣ Crear un README
echo "# Mi Proyecto" >> README.md

# 4️⃣ Agregar todos los archivos y hacer el primer commit
git add .
git commit -m "Primer commit"

# 5️⃣ Crear el repositorio en GitHub usando GitHub CLI (opcional, reemplaza nombre-repo)
# Si quieres privado, reemplaza --public por --private
gh repo create nombre-repo --public --source=. --remote=origin --push

# 6️⃣ Si no usas GitHub CLI, vincula el repo remoto manualmente
# git remote add origin https://github.com/usuario/nombre-repo.git
# git branch -M main
# git push -u origin main

# 7️⃣ Comandos básicos para continuar trabajando:
# git add .
# git commit -m "Descripción del cambio"
# git push

