# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).

Los datos confidenciales se gestionan mediante los secrets de Docker, cifran el dato y este se administra en el motor de docker. Los secrets pueden venir ya incluidos al crear el contenedor y también se pueden crear dependiendo de si docker cuenta con servicios Swarm, en caso de ser un contenedor individual se necesitan herramientas externas como Vault o AWS Secrets para poder gestionar datos sensibles o crear secrets, caso contrario se da a entender que tiene servicios Swarm y se puede crear secrets con el comando "docker secret create". De esta forma, docker se encarga de distribuir los secrets a contenedores especificos que necesiten el archivo, mostrando el archivo como un txt o archivo de solo lectura. Y es asi como pueden manipular o actualizar los secrets sin exponer datos confidenciales en variables de entorno. 
