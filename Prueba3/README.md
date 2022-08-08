# Prueba 3 - Zabalza

Para esta prueba se comenzó por crear un Dockerfile que describe una imagen de nginx, y lo único que hace es copiar el archivo index.html local dentro del directorio /usr/share/nginx/html, que es donde se almacena el index.html por defecto de nginx. El objetivo es que cada vez que se haga un push con el archivo index.html local modificado, se active un workflow de github actions que haga un build de la imagen utilizando la nueva versión del archivo, y que luego lo cargue en una cuenta de DockerHub.

Para esto se escribió el archivo buildAndPush.yaml localizado en el path .github/workflows.

Los pasos para verificar el correcto funcionamiento del pipeline son los siguientes:

    - Clonar el repositorio:

```bash
    git clone https://github.com/inakizabalza33/test-devops-Zabalza.git # Clonar el repositorio
```

    - Realizar una modificación al archivo index.html contenido dentro de la carpeta Prueba3 y guardar los cambios.

    - Agregar los cambios, hacer un commit y un push (sobre cualquier rama):

```bash
    git add . # Agregar los cambios
    git commit -m "Tu mensaje" # Realizar un commit
    git push origin main # Realizar un push. En este caso sobre main.
```

    Luego, en Github, podrá verse la action ejecutándose correctamente dentro del menu "Actions" del repositorio. 
