FROM ubuntu:16.04

#configuramos los host con ssh y autenticación por llaves

# Actualizamos la lista de paquetes
RUN apt-get update -y

# Instalamos pip, python, ssh
RUN apt-get install -y openssh-server python python-pip

#Configuramos la llave publica
# - Se crea la ubicacion donde se almacenará el docker del servicio ssh
RUN mkdir /var/run/sshd
# - Anexamos nuestra llave publica
COPY authorized_keys /root/.ssh/authorized_keys
# - Colocamos los permisos pertinentes a la llave [-xw-------]
RUN ["chmod","0600","/root/.ssh/authorized_keys"]

CMD ["/usr/sbin/sshd", "-D"]
