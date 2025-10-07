# Variables de Entorno
### ¿Qué son las variables de entorno?
# COMPLETAR
```
Son rutas que proporcionan información dinámica sobre el sistema operativo. Este especifica los directorios donde el sistema busca ejecutables. 
```

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETAR

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
<img width="924" height="132" alt="image" src="https://github.com/user-attachments/assets/1e4ed56b-7f31-4360-a85f-bbbb95cfb700" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR
```
docker run -P --name ContenedorMysql mysql
```

### ¿El contenedor se está ejecutando?
# COMPLETAR
Se para la ejecución del contenedor

### Identificar el problema
# COMPLETAR
El problema es que no se ha especificado una variable de entorno

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR
Se crea el contenedor con la contraseña de la variable
```
docker run -d -P --name MySqlCon -e MYSQL_ROOT_PASSWORD=sapito mysql
```
Se ingresa al contenedor
```
docker exec -it MySqlCon bash
```
Dentro de la base se ejecuta el siguiente comando y se ingresa la contraseña
```
mysql -u root -p
```
y una vez dentro de mysql con el comando "show databases;" se muestran las bases de datos existentes

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 
<img width="983" height="573" alt="image" src="https://github.com/user-attachments/assets/4206f597-b38e-4291-b1ed-c5a4fe9f4826" />

### ¿Qué bases de datos existen en el contenedor creado? 

# COMPLETAR
1. information_schema
2. mysql
3. performance_schema
4. sys  
