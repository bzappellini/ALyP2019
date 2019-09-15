# ALyP2019
Aspectos legales y profesionales

# Ejemplo de app con docker y django

*Nota: este ejemplo fue tomado des este sitio: [https://docs.docker.com/compose/django/]
(https://docs.docker.com/compose/django/)*

En el directorio docker-django hay tres archivo:
* **requirements.txt:** Paquetes a instalar en la imagen docker
* **Dockerfile:** para construir la imagen con docker y django
* **docker-compose.yml:** para construir el ambiente de ejecución

### Primero hay que crear el proyecto django:

´´´
sudo docker-compose run web django-admin startproject proyectoejemplo .
´´´

### Luego cambiar los permisos de los archivos:

sudo chown -R $USER:$USER .

### Conectar la base de datos

En esta sección, configurará la conexión de la base de datos para Django.

1. En el directorio de su proyecto, edite el *composeexample/settings.py* archivo.

2. Reemplace el DATABASES = ... con lo siguiente:

´´´
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}
´´´
### Ejecutar

$ docker-compose up
