# Dockerfile
FROM delfer/alpine-ftp-server

# Ajouter le groupe et l'utilisateur www-data avec UID=33 et GID=33
RUN addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data

# Assurer les permissions correctes pour le répertoire partagé
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration finale et démarrage du serveur FTP
CMD ["/run.sh"]
