FROM delfer/alpine-ftp-server

# Configuration de l'utilisateur et des permissions
RUN \
  mkdir -p /var/www/html && \
  chown -R www-data:www-data /var/www/html && \
  chmod -R g+rw /var/www/html && \
  chmod g+s /var/www/html

# Commande d'exécution pour garantir les permissions à chaque démarrage
ENTRYPOINT ["sh", "-c", "chown -R www-data:www-data /var/www/html && chmod -R g+rw /var/www/html && chmod g+s /var/www/html && exec /run.sh"]