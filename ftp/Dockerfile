FROM debian:bullseye-slim

# Installer vsftpd
RUN apt-get update && apt-get install -y \
    vsftpd \
    && rm -rf /var/lib/apt/lists/*

# Créer le répertoire `secure_chroot_dir`
RUN mkdir -p /var/run/vsftpd/empty && \
    chmod 755 /var/run/vsftpd/empty

# Configuration des permissions sur /var/www/html
RUN mkdir -p /var/www/html && \
    chmod -R 775 /var/www/html && \
    chmod g+s /var/www/html

# Copier un fichier de configuration personnalisé pour vsftpd
COPY vsftpd.conf /etc/vsftpd.conf

# Exposer les ports FTP
EXPOSE 21 21000-21010

# Lancer vsftpd
CMD ["/usr/sbin/vsftpd", "/etc/vsftpd.conf"]