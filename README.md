--------COMANDOS PARCIAL--------

PARTE I

Parte 1: Acceso remoto 20%
✓ Seleccionen una de las máquinas virtuales de su equipo para el desarrollo del parcial.
✓ Elegir un modo de acceso visto en clases (Telnet o ssh) que desee utilizar e Instale y
configure las características necesarias para el acceso remoto.
✓ Actualizar la base de datos y los paquetes del sistema.
✓ Acceder desde la maquina cliente al servidor debian para realizar la parte 2. Puede
hacer uso de Putty para el acceso

Comandos
#Iniciaremos en la maquina virtual 

#Ingresamos con nuestras credenciales y luego como usuario root con:

su -

#Actualizamos la base de datos y los paquetes

apt update
apt upgrade

#Verificaremos nuestra dirección ip de la maquina.

ip a

#Nos conectaremos mediante Telnet. Abrimos PuTTY e ingresamos por SSH colocando la dirección ip que obtuvimos (192.168.123.131)


PARTE II

Parte 2: Gestión de usuarios y grupos 30%
La empresa “M&A Technologies”, le solicita crear los siguientes grupos:
• Recursos Humanos (RH)
• Administración (ADMON)
• Operaciones
Crear 9 usuarios, 3 usuarios para cada uno de los grupos. (Se recomienda adduser)

#Creamos los tres Grupos requeridos 

groupadd RH
groupadd ADMON
groupadd operaciones

#Verificamos 

cat /etc/groups

#Creacion de los 9 usuarios 

adduser fati
adduser moi
adduser carm
adduser antonio
adduser edgardo
adduser fernando
adduser nadia
adduser hector
adduser lucia

#Verificamos la creación de los usuarios

cat /etc/passwd

#Asignamos los usuarios a cada grupo

adduser fati RH
adduser moi RH
adduser carm RH
adduser antonio ADMON
adduser edgardo ADMON
adduser fernando ADMON
adduser nadia operaciones
adduser hector operaciones
adduser lucia operaciones


#Crearemos un Archivo para cada usuario 
#Para fati
#Ingresamos al usuario

#Luego a los archivos del Usuario 

cd /home/fati

#Creamos el archivo

touch Empleados.txt

#Aplicamos los permisos 

chmod 666 Empleados.txt

#Verificamos 

ls -l


#Para moi
#Ingresamos al usuario 
#Luego a los archivos del Usuario 

cd /home/moi

#Creamos el archivo

touch app.sh

#Aplicamos los permisos 

chmod 711 app.sh

#Verificamos 

ls -l


#Para carm
#Ingresamos al usuario
#Luego a los archivos del Usuario 

cd /home/carm

#Creamos el archivo

touch Planilla.pdf

#Aplicamos los permisos 

chmod 754 Planilla.pdf

#Verificamos 

ls -l


#Para antonio
#Ingresamos al usuario
#Luego a los archivos del Usuario 

cd /home/antonio

#Creamos el archivo

touch Calendarización.docx

#Aplicamos los permisos 

chmod 755 Calendarización.docx

#Verificamos 

ls -l

#Para edgardo
#Ingresamos al usuario 
#Luego a los archivos del Usuario 
#Creamos el archivo

touch Logo.png

#Aplicamos los permisos 

chmod 777 Logo.png

#Verificamos 

ls -l

#Para fernando
#Ingresamos al usuario 
#Creamos el archivo

touch Capacitaciones.xlsx

#Aplicamos los permisos 

chmod 744 Capacitaciones.xlsx

#Verificamos 

ls -l

#Para nadia
#Ingresamos al usuario
#Creamos el archivo

touch Permisos.docx

#Aplicamos los permisos 

chmod 640 Permisos.docx

#Verificamos 

ls -l

#Para hector
#Ingresamos al usuario hector
#Creamos el archivo

touch Roles-semana1.pdf

#Aplicamos los permisos 

chmod 400 Roles-semana1.pdf
#Verificamos 

ls -l

#Para lucia
#Ingresamos al usuario
#Creamos el archivo

touch Filosofía.mp4

#Aplicamos los permisos 

chmod 545 Filosofía.mp4

#Verificamos 

ls -l

Parte 3: Transferencia de archivos 20%
La empresa M&A Technologies también necesita realizar una copia del archivo llamado
salarios (que se compartirá en el siguiente enlace para su descarga) donde se 
encuentra información sensible, para ello se requiere del uso del protocolo scp para 
realizar la transferencia al servidor. Asigné permiso de Lectura y escritura para el usuario 
3 de RH y permisos de lectura para el grupo y ninguno para el resto

#Hacemos la transferencia del archivo

cd C:\Users\ftaya\Escritorio
Luego, ejecutamos el siguiente comando:
scp salarios.pdf fatima@192.168.123.131:/home/fatima

#Dentro del Usuario cambiamos los permisos

chmod 640 salarios.pdf