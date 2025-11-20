# Pasos para crear un repositorio Git

## 1. Inicializar el repositorio

-   Abre tu terminal.
-   Navega a la carpeta de tu proyecto:

``` bash
cd ruta/al/proyecto
```

-   Inicializa el repositorio:

``` bash
git init
```

## 2. Agregar archivos al área de preparación

-   Agrega todos los archivos:

``` bash
git add .
```

-   O agrega un archivo específico:

``` bash
git add nombre_archivo
```

## 3. Realizar el primer commit

``` bash
git commit -m "Primer commit"
```

## 4. Conectar con un repositorio remoto (por ejemplo, GitHub)

``` bash
git remote add origin https://github.com/usuario/repositorio.git
```

## 5. Subir los cambios al repositorio remoto

``` bash
git push -u origin main
```
