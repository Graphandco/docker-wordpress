FROM delfer/alpine-ftp-server

# Configuration de www-data avec UID et GID standard (33)
RUN \
  echo "Création de l'utilisateur et du groupe www-data" && \
  addgroup -g 33 www-data && \
  adduser -D -u 33 -G www-data www-data && \
  mkdir -p /var/www/html && \
  chown -R www-data:www-data /var/www/html && \
  chmod -R g+rw /var/www/html && \
  chmod g+s /var/www/html

# Application des permissions lors de l'exécution du conteneur
ENTRYPOINT ["sh", "-c", "chown -R www-data:www-data /var/www/html && exec /run.sh"]
