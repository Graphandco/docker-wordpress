FROM delfer/alpine-ftp-server

# Création ou vérification de l'utilisateur www-data
RUN \
    if ! id -u www-data >/dev/null 2>&1; then \
        if ! getent passwd 33 >/dev/null 2>&1 && ! getent group 33 >/dev/null 2>&1; then \
            addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
        else \
            echo "Conflit avec UID/GID 33. Assignation temporaire pour www-data."; \
            addgroup -g 1001 www-data && adduser -D -u 1001 -G www-data www-data; \
        fi; \
    fi

# Création du répertoire avec les permissions
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
