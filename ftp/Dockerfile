FROM delfer/alpine-ftp-server

# Création de l'utilisateur et du groupe www-data
RUN addgroup -g 33 www-data && \
    adduser -u 33 -D -G www-data www-data

# Configuration des permissions sur /var/www/html
RUN mkdir -p /var/www/html && \
    chown -R www-data:www-data /var/www/html && \
    chmod -R g+rw /var/www/html && \
    chmod g+s /var/www/html

# Commande d'exécution pour garantir les permissions à chaque démarrage
ENTRYPOINT ["sh", "-c", "chown -R www-data:www-data /var/www/html && chmod -R g+rw /var/www/html && chmod g+s /var/www/html && exec /run.sh"]