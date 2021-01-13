# Boilerplate de Prestashop

## Instalación

### Requerimientos

* Docker

Preferentemente configurar el dominio del servidor antes de instalar prestashop.

### Método de instalación

1. Hacer fork del repositorio

2. Clonar repositorio en local

3. Accede a la carpeta raíz del proyecto

4. Crear archivo `.env`
```
> cp .env.example .env
```

Modificar datos del archivo `.env`

5. Construye el docker
```
> docker-compose build
```

6. Levanta el docker
```
> docker-compose up -d
```

7. Ejecutar el archivo init-letsencrypt.sh que se encuentra en la carpeta raiz del proyecto

8. Dar permisos de ejecucion a la carpeta prestashop que se encuentra en la raiz del proyecto `chmod 777 ./prestashop`

9. Accede a la url asignada a tu proyecto desde el navegador

10. Configura el proyecto desde la guía de prestashop en el navegador

11. Modificar el archivo de configuración de nginx en ./docker/nginx/sites/default.conf

Cambiar el texto `/admin/` por el nombre de la carpeta admin generado en la instalación de prestashop

12. Elimina la carpeta `/install` del directorio `./presathop/install/`

13. En Backoffice guardar como SI la opcion en Configurar > Configuracion > Activar SSL

14. En Backoffice guardar como SI la opcion en Configurar > Configuracion > Activar SSL en todas las páginas
