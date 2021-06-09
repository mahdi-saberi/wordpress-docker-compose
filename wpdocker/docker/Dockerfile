FROM dockerhub.ir/wordpress:php7.2-apache
#RUN export HTTP_PROXY=user:pass@ip:port

# RUN apt-get clean
# RUN apt-get update
RUN curl -fsSL 'https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz' -o ioncube.tar.gz \ 
&& mkdir -p /tmp/ioncube \ 
&& tar -xvvzf ioncube.tar.gz \ 
&& mv ioncube/ioncube_loader_lin_7.2.so `php-config --extension-dir` \ 
&& rm -Rf ioncube.tar.gz ioncube \ 
&& docker-php-ext-enable ioncube_loader_lin_7.2
