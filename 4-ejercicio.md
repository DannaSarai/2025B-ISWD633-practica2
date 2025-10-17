## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR
```
docker network create net-wp -d bridge
```

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR
```
docker run -d --name mysqlCont --network net-wp -e MYSQL_ROOT_PASSWORD=sapitos -e MYSQL_DATABASE=bdd -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin123 mysql:8
```

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
```
docker run -d --name wordpressCont --network net-wp -p 8080:80 -e WORDPRESS_DB_HOST=mysqlCont:3306 -e WORDPRESS_DB_USER=admin -e WORDPRESS_DB_PASSWORD=admin123 -e WORDPRESS_DB_NAME=bdd wordpress
```

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es 8080

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
<img width="2567" height="1641" alt="image" src="https://github.com/user-attachments/assets/4768c8ce-a2f6-47fa-922d-523caa36fcf6" />

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="3181" height="1781" alt="image" src="https://github.com/user-attachments/assets/37e3dec2-8803-48f9-a60f-a7472c7ada62" />


### Eliminar el contenedor wordpress
# COMPLETAR
```
docker rm -f wordpressCont
```
<img width="516" height="109" alt="image" src="https://github.com/user-attachments/assets/38fecf94-91fe-497f-b279-acb828397aa0" />

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR
Al ingresar nuevamente, me pide datos y al ingresarlos me manda directo a una pagina con el mismo nombre del sitio que tenia anteriormente pero no existe la publicacion o información alguna.
