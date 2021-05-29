FROM wordpress:${WORDPRESS_VERSION:-latest}

RUN apt-get clean
RUN apt-get update
RUN curl -fsSL 'https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz' -o ioncube.tar.gz \ 
&& mkdir -p /tmp/ioncube \ 
&& tar -xvvzf ioncube.tar.gz \ 
&& mv ioncube/ioncube_loader_lin_7.4.so `php-config --extension-dir` \ 
&& rm -Rf ioncube.tar.gz ioncube \ 
&& docker-php-ext-enable ioncube_loader_lin_7.4