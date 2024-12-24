FROM delfer/alpine-ftp-server

# Vérifier si un utilisateur/groupe existe déjà pour UID 33 et le gérer
RUN \
    if ! id -u www-data >/dev/null 2>&1; then \
        if ! grep -q ':33:' /etc/passwd && ! grep -q ':33:' /etc/group; then \
            addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
        else \
            echo "UID ou GID 33 déjà utilisé par un autre utilisateur/groupe."; \
            EXISTING_USER=$(getent passwd 33 | cut -d: -f1 || true); \
            EXISTING_GROUP=$(getent group 33 | cut -d: -f1 || true); \
            echo "Utilisateur existant: $EXISTING_USER, Groupe existant: $EXISTING_GROUP"; \
            deluser "$EXISTING_USER" 2>/dev/null || true; \
            delgroup "$EXISTING_GROUP" 2>/dev/null || true; \
            addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
        fi; \
    fi

# Créer le répertoire et attribuer les droits
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
