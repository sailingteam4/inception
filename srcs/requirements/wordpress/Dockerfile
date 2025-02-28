# Utiliser l'image Debian Bullseye comme base
FROM debian:bullseye

# Installer les dépendances nécessaires pour ajouter le dépôt PHP
RUN apt-get update && apt-get install -y \
    lsb-release \
    ca-certificates \
    apt-transport-https \
    curl \
    gnupg2 \
    && curl -fsSL https://packages.sury.org/php/README.txt | bash -x \
    && apt-get update

# Installer PHP 8.2 et PHP-FPM
RUN apt-get install -y php8.2 php8.2-fpm

# Vérifier l'installation de PHP et PHP-FPM
RUN php -v
RUN php-fpm -v

# Vérifier l'emplacement des binaires PHP (pour le débogage)
RUN ls -l /usr/sbin/php*

# Utiliser php-fpm comme commande par défaut
CMD ["php-fpm", "-F"]
