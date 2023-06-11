FROM centos:8

RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*.repo && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=https://vault.centos.org|g' /etc/yum.repos.d/CentOS-*.repo && \
    yum -y update && \
    yum -y install httpd

ADD webserver.tar.gz /var/www/html/

CMD [ "-D", "FOREGROUND" ]

ENTRYPOINT [ "usr/sbin/httpd" ]

EXPOSE 80