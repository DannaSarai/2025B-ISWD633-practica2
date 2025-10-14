### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
# COMPLETAR
```
docker run -d --name postgresCont -e POSTGRES_PASSWORD=sapitos postgres:15-alpine3.21
```

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

# COMPLETAR
```
docker run -d --name pgAdmin -e PGADMIN_DEFAULT_EMAIL=admin@admin.com -e PGADMIN_DEFAULT_PASSWORD=sapitos -p 5050:80 dpage/pgadmin4
```

La figura presenta el esquema creado en donde los puertos son:
- a: 5050
- b: 5432
- c: 80

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN
<img width="1912" height="1039" alt="image" src="https://github.com/user-attachments/assets/11d6130b-6207-4932-814b-359024aec3ad" />

Antes de ingresar al servidor desde localhost de postgres se debe crear una conexión 
```
docker network create netPostgres
docker network connect netPostgres postgresCont
docker network connect netPostgres pgAdmin
```

Ingreso al servidor creado
<img width="1486" height="1241" alt="image" src="https://github.com/user-attachments/assets/8546d701-92f1-4c6a-9ac1-45a07da97ef4" />

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

Se crea la base de datos, la tabla y se agregan registros
```
CREATE DATABASE info;
```
```
CREATE TABLE personas (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(50)
);
```
Datos insertados (añadiendo mi nombre)
```
INSERT INTO personas (nombre) VALUES ('Danna Morales');
INSERT INTO personas (nombre) VALUES ('Javier Muñoz'); 
```
<img width="1482" height="528" alt="image" src="https://github.com/user-attachments/assets/6c9fd4d6-01c3-4e77-a114-0be560f34b04" />

## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR
```
\c info
```

### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
<img width="385" height="154" alt="image" src="https://github.com/user-attachments/assets/37a6e19f-71a3-4899-a5d2-411398bf2a36" />

