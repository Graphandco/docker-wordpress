FROM delfer/alpine-ftp-server

# Vérification et création de l'utilisateur et du groupe www-data uniquement s'ils n'existent pas
RUN if ! getent group 33 >/dev/null; then addgroup -g 33 www-data; fi && \
    if ! getent passwd 33 >/dev/null; then adduser -u 33 -D -G www-data www-data; fi

# Configuration des permissions sur /var/www/html
RUN mkdir -p /var/www/html && \
    chown -R www-data:www-data /var/www/html && \
    chmod -R g+rw /var/www/html && \
    chmod g+s /var/www/html

# Commande d'exécution pour garantir les permissions à chaque démarrage
ENTRYPOINT ["sh", "-c", "chown -R www-data:www-data /var/www/html && chmod -R g+rw /var/www/html && chmod g+s /var/www/html && exec /run.sh"]