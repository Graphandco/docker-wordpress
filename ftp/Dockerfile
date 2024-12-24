FROM delfer/alpine-ftp-server

# Création explicite de l'utilisateur www-data avec UID et GID spécifiques
RUN \
    if ! getent passwd 33 >/dev/null 2>&1; then \
        addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    else \
        echo "UID 33 déjà utilisé, utilisateur existant : $(getent passwd 33 | cut -d: -f1)"; \
    fi

# Préparer le dossier et appliquer les permissions
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Définir l'utilisateur par défaut pour le conteneur FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
