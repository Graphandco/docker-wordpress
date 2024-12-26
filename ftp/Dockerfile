FROM debian:bullseye-slim

# Installer un serveur FTP léger
RUN apt-get update && apt-get install -y \
    vsftpd \
    && rm -rf /var/lib/apt/lists/*

# Configuration de l'utilisateur et des permissions
RUN mkdir -p /var/www/html && \
    chmod -R 775 /var/www/html && \
    chmod g+s /var/www/html

# Copier un fichier de configuration personnalisé pour vsftpd
COPY vsftpd.conf /etc/vsftpd.conf

# Exposer les ports FTP
EXPOSE 21 21000-21010

# Lancer vsftpd
CMD ["/usr/sbin/vsftpd", "/etc/vsftpd.conf"]