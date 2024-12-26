FROM delfer/alpine-ftp-server

# Assure que le répertoire existe et configure les permissions directement
RUN mkdir -p /var/www/html && \
    chmod -R 775 /var/www/html && \
    chmod g+s /var/www/html && \
    apk add --no-cache shadow && \
    groupmod -g 33 ftp && \
    usermod -u 33 -g 33 ftp

# Commande d'exécution pour garantir les permissions à chaque démarrage
ENTRYPOINT ["sh", "-c", "chmod -R 775 /var/www/html && chmod g+s /var/www/html && exec /run.sh"]