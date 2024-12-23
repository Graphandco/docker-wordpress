FROM delfer/alpine-ftp-server

# Vérifier si un utilisateur avec l'UID 33 existe déjà, sinon le créer
RUN \
    if ! id -u www-data >/dev/null 2>&1; then \
        if ! getent passwd 33 >/dev/null 2>&1; then \
            addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
        else \
            USER=$(getent passwd 33 | cut -d: -f1); \
            echo "Utilisateur avec UID 33 trouvé : $USER. Utilisation existante."; \
        fi; \
    fi

# Assurer les permissions correctes pour le répertoire partagé
RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html

# Configuration finale et démarrage du serveur FTP
CMD ["/run.sh"]
