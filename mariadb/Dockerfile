FROM debian:bullseye

# Instala MariaDB y define la contraseña de root
RUN apt-get update && \
    DEBIAN_FRONTEND="noninteractive" apt-get install -y mariadb-server && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    echo "mariadb-server-10.5 mysql-server/root_password password your_password" | debconf-set-selections && \
    echo "mariadb-server-10.5 mysql-server/root_password_again password your_password" | debconf-set-selections

# Expone el puerto 3306 para conexiones externas
EXPOSE 3306

# Comando para iniciar MariaDB al iniciar el contenedor
CMD ["mysqld", "--user=mysql", "--console"]
