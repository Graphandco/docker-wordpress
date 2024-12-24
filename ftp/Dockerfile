FROM delfer/alpine-ftp-server

# Vérifier si un utilisateur avec l'UID 33 existe déjà
RUN \
    if ! getent passwd 33 >/dev/null 2>&1; then \
        addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    else \
        echo "UID 33 déjà utilisé par l'utilisateur $(getent passwd 33 | cut -d: -f1), aucun changement effectué."; \
    fi && \
    mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
