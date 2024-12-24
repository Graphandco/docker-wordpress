FROM delfer/alpine-ftp-server

# Vérification et création de l'utilisateur et du groupe si nécessaire
RUN \
    if ! getent passwd 33 >/dev/null; then \
        addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    else \
        echo "Utilisateur avec UID 33 existe déjà."; \
    fi

# Préparation du répertoire avec les bonnes permissions
RUN mkdir -p /var/www/html && chown -R 33:33 /var/www/html

# Configuration finale
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
