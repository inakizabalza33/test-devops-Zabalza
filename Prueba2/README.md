# Prueba 2 - Zabalza Inaki

Para esta prueba, se generaron dos dockerfiles:

- Uno para el backend, que usa una imagen de python, instala algunas librerías faltantes para el correcto funcionamiento, y luego corre un entrypoint, el cual realiza las migraciones e inicia el servidor. Las librerías que fueron instaladas adicionalmente luego de verificar que faltaban fueron: gcc, python3-dev, graphviz, libgraphviz-dev y pkg-config.

- Otro para el frontend, que utiliza una imagen de node, instala la librería "chalk", puesto que al intentar correr el contenedor ocurría un error diciendo que faltaba instalar dicha dependencia. Luego inicia el servidor corriendo "npm start".

Finalmente, se confeccionó un docker-compose.yml, el cual realiza el build y el run de los contenedores anteriormente descritos, abriendo el puerto 8000 para el backend y el 3000 para el frontend. Este script también corre una imagen de postgres, implementando una base de datos relacional que se comunicará con el backend a través del puerto 5432, y persistirá los datos dentro del directorio database-data.

Para probar que los servicios se encuentran corriendo correctamente, deberán seguirse los siguientes pasos:

- Clonar el repositorio:

```bash
    git clone https://github.com/inakizabalza33/test-devops-Zabalza.git # Clonar el repositorio
```

- Ubicado dentro de la carpeta del repositorio, moverse al directorio Prueba2 y correr el docker compose:

```bash
    cd Prueba2 # Moverse al directorio Prueba2
    docker-compose up -d # Construir y correr los contenedores mediante docker compose
```

Luego, será posible conectarse a los puertos correspondientes y visualizar tanto el frontend como el backend de la aplicación:

- En el caso de que se haya corrido el script en un entorno local, ir al navegador y buscar:
 
```bash
    localhost:8000 # Para visualizar el backend
    localhost:3000 # Para visualizar el frontend
```

- En el caso de que se haya corrido el script en un entorno cloud o en otro servidor, ir al navegador y buscar (reemplanzando <ip_del_server> por la ip de la instancia en la nube o servidor utilizado):

```bash
    <ip_del_server>:8000 # Para visualizar el backend
    <ip_del_server>:3000 # Para visualizar el frontend
```
