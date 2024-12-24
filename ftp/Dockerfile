FROM delfer/alpine-ftp-server

# Vérification et gestion des utilisateurs
RUN \
    if ! getent passwd 33 >/dev/null 2>&1; then \
        echo "Création de www-data avec UID 33"; \
        addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    else \
        EXISTING_USER=$(getent passwd 33 | cut -d: -f1); \
        echo "UID 33 déjà utilisé par l'utilisateur : $EXISTING_USER"; \
        if [ "$EXISTING_USER" != "www-data" ]; then \
            echo "Les UID 33 sont requis pour www-data mais utilisés par $EXISTING_USER, veuillez corriger."; \
            exit 1; \
        fi; \
    fi

# Créer le répertoire et attribuer les permissions
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
