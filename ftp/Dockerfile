FROM delfer/alpine-ftp-server

# Créer l'utilisateur www-data avec UID et GID standard
RUN \
    if ! getent passwd www-data >/dev/null 2>&1; then \
        addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    fi && \
    mkdir -p /var/www/html && \
    chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
