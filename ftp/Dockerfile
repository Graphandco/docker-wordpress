FROM delfer/alpine-ftp-server

# Vérifier si l'utilisateur www-data existe déjà en utilisant 'id'
RUN id -u www-data &>/dev/null || (addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data)

# Créer le répertoire et donner les bons droits à www-data
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
