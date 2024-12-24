FROM delfer/alpine-ftp-server

# Variables pour l'UID et le GID
ARG UID=33
ARG GID=33

# Création ou mise à jour de l'utilisateur www-data
RUN \
    if ! id -u www-data >/dev/null 2>&1; then \
        if ! getent passwd ${UID} >/dev/null 2>&1 && ! getent group ${GID} >/dev/null 2>&1; then \
            echo "Création de www-data avec UID=${UID} et GID=${GID}"; \
            addgroup -g ${GID} www-data && adduser -D -u ${UID} -G www-data www-data; \
        else \
            echo "Conflit détecté avec UID=${UID} ou GID=${GID}. Utilisation de valeurs temporaires."; \
            addgroup -g 1001 www-data && adduser -D -u 1001 -G www-data www-data; \
        fi; \
    else \
        echo "Utilisateur www-data déjà présent"; \
    fi

# Préparer le dossier et appliquer les permissions
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
