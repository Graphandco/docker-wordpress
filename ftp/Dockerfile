FROM delfer/alpine-ftp-server

# Variables pour l'UID et le GID
ARG UID=33
ARG GID=33

# Création de l'utilisateur et du groupe www-data
RUN \
    if ! id -u www-data >/dev/null 2>&1; then \
        echo "Création de www-data"; \
        addgroup -g ${GID} www-data || addgroup -g 1001 www-data; \
        adduser -D -u ${UID} -G www-data www-data || adduser -D -u 1001 -G www-data www-data; \
    fi

# Création du répertoire et application des droits
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration des utilisateurs FTP
ENV USERS=ftpusergraphandco|1FTPvmQ2tl@@AZ|/var/www/html
