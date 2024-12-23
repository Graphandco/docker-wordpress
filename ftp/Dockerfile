FROM delfer/alpine-ftp-server

# Créez le groupe www-data si nécessaire
RUN getent group www-data || addgroup -g 33 www-data

# Créez l'utilisateur www-data si nécessaire
RUN id -u www-data || adduser -D -u 33 -G www-data www-data

# Assurer les permissions correctes pour le répertoire partagé
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration finale et démarrage du serveur FTP
CMD ["/run.sh"]
