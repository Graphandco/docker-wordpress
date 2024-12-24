FROM delfer/alpine-ftp-server

# Vérification et création de l'utilisateur www-data avec UID/GID spécifiques
RUN \
    if ! getent passwd 33 >/dev/null 2>&1; then \
        addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    else \
        echo "UID 33 déjà utilisé, utilisateur existant : $(getent passwd 33 | cut -d: -f1)"; \
        EXISTING_USER=$(getent passwd 33 | cut -d: -f1); \
        if [ "$EXISTING_USER" != "www-data" ]; then \
            echo "Renommage de l'utilisateur $EXISTING_USER en www-data"; \
            deluser "$EXISTING_USER"; \
            addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
        fi; \
    fi

# Préparer le dossier et attribuer les permissions
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Variables pour la configuration FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
