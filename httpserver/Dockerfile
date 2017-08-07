FROM ubuntu:16.04

RUN apt-get update -y \
      && apt-get install -y apache2 apache2-utils libexpat1 ssl-cert python \
      && apt-get install -y libapache2-mod-wsgi \
      && apt-get install -y python-pip \
      && pip -V \
      && apt-get install wget -y \
      && wget -O /etc/apache2/conf-available/wsgi.conf "https://rawgit.com/chuangzl/Container/master/wsgi.conf" \
      && wget -O /etc/apache2/apache2.conf "https://rawgit.com/chuangzl/Container/master/apache2.conf" \
      && service apache2 restart \
      && service apache2 reload \
      && a2enconf wsgi \
      && service apache2 restart \
      && pip install --upgrade pip \
      && pip install web.py \
      && pip install requests 

CMD ["service apache2 start"]

      
