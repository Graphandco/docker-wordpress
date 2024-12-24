FROM delfer/alpine-ftp-server

# Créer www-data si nécessaire et assigner les permissions
RUN \
  if ! id -u www-data >/dev/null 2>&1; then \
    if ! getent passwd 33 >/dev/null 2>&1 && ! getent group 33 >/dev/null 2>&1; then \
      echo "Création de www-data avec UID=33 et GID=33"; \
      addgroup -g 33 www-data && adduser -D -u 33 -G www-data www-data; \
    else \
      echo "Conflit détecté avec UID=33 ou GID=33. Utilisation de valeurs temporaires."; \
      addgroup -g 1001 www-data && adduser -D -u 1001 -G www-data www-data; \
    fi; \
  else \
    echo "Utilisateur www-data déjà présent"; \
  fi && \
  mkdir -p /var/www/html && \
  chown -R www-data:www-data /var/www/html && \
  chmod g+s /var/www/html && \
  find /var/www/html -type d -exec chmod g+s {} \;
