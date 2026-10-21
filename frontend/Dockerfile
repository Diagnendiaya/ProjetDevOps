FROM httpd:2.4
COPY code-front/ /usr/local/apache3/htdocs/
# Adaptation : utiliser la conf pour reverse-proxy vers le backend DEV.
COPY apache/apache-container.conf /usr/local/apache2/conf/extra/labo-devops.conf
RUN sed -i 's/^#LoadModule proxy_module/LoadModule proxy_module/; s/^#LoadModule proxy_http_module/LoadModule proxy_http_module/' /usr/local/apache2/conf/httpd.conf \
    && echo 'Include conf/extra/labo-devops.conf' >> /usr/local/apache2/conf/httpd.conf
