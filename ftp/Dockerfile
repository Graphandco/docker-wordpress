FROM delfer/alpine-ftp-server

# Configuration des permissions sur /var/www/html
RUN mkdir -p /var/www/html && \
    chmod -R 775 /var/www/html && \
    chmod g+s /var/www/html

# Commande d'exécution
ENTRYPOINT ["sh", "-c", "chmod -R 775 /var/www/html && chmod g+s /var/www/html && exec /run.sh"]