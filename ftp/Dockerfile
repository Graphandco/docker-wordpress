FROM delfer/alpine-ftp-server

# Configuration de l'utilisateur et des permissions
RUN \
  mkdir -p /var/www/html && \
  chown -R 33:33 /var/www/html && \
  chmod -R g+rw /var/www/html && \
  chmod g+s /var/www/html

# Commande d'exécution pour garantir les permissions à chaque démarrage
ENTRYPOINT ["sh", "-c", "chown -R 33:33 /var/www/html && chmod -R g+rw /var/www/html && chmod g+s /var/www/html && exec /run.sh"]
