# Global Laravel Application Deployer Dockerfile For WEBLANKAN v1.0.3 by Lahiru

# Use PHP 5.6 with Apache
FROM php:5.6-apache

# Maintainer information
LABEL maintainer="Lahiru"

# Install System Dependencies
RUN apt-get update && apt-get install -y \
    libzip-dev \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libonig-dev \
    libxml2-dev \
    libssl-dev \
    openssl \
    zip \
    unzip \
    git \
    curl \
    nano \

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Enable Apache mod_rewrite for URL rewriting
RUN a2enmod rewrite

# Set PHP Configuration Options
RUN echo "expose_php = Off\n" \
    "memory_limit = 512M\n" \
    "upload_max_filesize = 50M\n" \
    "post_max_size = 50M\n" \
    "max_execution_time = 180\n" \
    "max_input_time = 300\n" \
    "max_input_vars = 10000\n" \
    "opcache.memory_consumption=128\n" \
    "opcache.interned_strings_buffer=8\n" \
    "opcache.max_accelerated_files=4000\n" \
    "opcache.revalidate_freq=2\n" \
    "opcache.fast_shutdown=1\n" \
    > /usr/local/etc/php/conf.d/php-optimizations.ini