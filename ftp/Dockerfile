FROM delfer/alpine-ftp-server

# Créer un utilisateur et un groupe partagé pour WordPress et FTP
RUN \
  echo "Création de l'utilisateur et du groupe communs avec UID=1000 et GID=1000" && \
  addgroup -g 1000 sharedgroup && \
  adduser -D -u 1000 -G sharedgroup shareduser && \
  mkdir -p /var/www/html && \
  chown -R shareduser:sharedgroup /var/www/html && \
  chmod -R g+rw /var/www/html && \
  chmod g+s /var/www/html
