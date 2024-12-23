FROM delfer/alpine-ftp-server

# Vérifier si un utilisateur avec l'UID 33 existe déjà
RUN \
    USER=$(getent passwd 33 | cut -d: -f1); \
    if [ "$USER" = "" ]; then \
        addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    else \
        echo "Utilisateur avec UID 33 trouvé : $USER. Utilisation existante."; \
    fi && \
    mkdir -p /var/www/html && chown -R $USER:$USER /var/www/html
