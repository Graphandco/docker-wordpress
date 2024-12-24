FROM delfer/alpine-ftp-server

# Variables pour l'UID et le GID
ARG UID=33
ARG GID=33

# Création ou vérification de l'utilisateur www-data avec UID/GID dynamiques
RUN \
    if ! id -u www-data >/dev/null 2>&1; then \
        if ! getent passwd ${UID} >/dev/null 2>&1 && ! getent group ${GID} >/dev/null 2>&1; then \
            addgroup -g ${GID} www-data && adduser -D -u ${UID} -G www-data www-data; \
        else \
            echo "Conflit avec UID ${UID} ou GID ${GID}. Assignation temporaire pour www-data."; \
            addgroup -g 1001 www-data && adduser -D -u 1001 -G www-data www-data; \
        fi; \
    fi

# Création du répertoire avec les permissions
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
