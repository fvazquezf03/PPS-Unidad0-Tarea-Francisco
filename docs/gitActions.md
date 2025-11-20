# GitHub Actions – Generación automática de documentación

## 1.Configuración de MkDocs
- Crea un archivo llamdo mkdocs.yml
``` bash
# mkdocs.yml

# -------------------------------------------------------------
# CONFIGURACIÓN GENERAL DEL SITIO
# -------------------------------------------------------------
site_name: Documentación de Calculadora Python

# -------------------------------------------------------------
# ESTRUCTURA DE NAVEGACIÓN (MENÚ)
# -------------------------------------------------------------
# Define la lista de enlaces y el orden de aparición en el menú de navegación principal.
nav:
  - Inicio: index.md
  - Git: git.md
  - GitHub Actions: gitActions.md
  - GitHub Pages: gitPages.md
  - Docker: docker.md
  - Conclusiones: conclusiones.md
  # Se pueden añadir subsecciones anidando listas:
  # - Referencia:
  #     - Funciones: referencia/funciones.md
  #     - Clases: referencia/clases.md

# -------------------------------------------------------------
# DIRECTORIOS
# -------------------------------------------------------------
docs_dir: docs 
```
# El Paso 2 Configuración de la Pipeline
1.Creación del Workflow: Dentro del directorio .github/, crea el directorio workflows/ y dentro de él, el archivo deploy_docs.yml
2.Dentro del archivo deploy_docs.yml ponemos lo siguiente
```bash
name: Deploy MkDocs
on:
  push:
    branches: [main]
permissions:
  contents: write
  pages: write
  id-token: write
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repo
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.x'

      - name: Install dependencies
        run: |
          pip install mkdocs
          pip install mkdocs-material

      - name: Deploy docs
        run: mkdocs gh-deploy --force
        env:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
#Paso 3: Vamos a ejecutarlo para comprobar que funciona
1. Hacemos un commit
```bash
git add .
git commit -m " Configuración de MkDocs y pipeline"
git push origin main
```
2. Lo comprobamos en github

<img width="393" height="192" alt="image" src="https://github.com/user-attachments/assets/375f1c0d-9c92-4a71-9b98-2d181a8fd278" />

