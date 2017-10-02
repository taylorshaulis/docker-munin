FROM phusion/baseimage:0.9.22

RUN apt-get update --fix-missing
RUN apt-get install -y apache2 apache2-utils libcgi-fast-perl libapache2-mod-fcgid

COPY apache.conf /munin.apache.conf
RUN cat /munin.apache.conf >> /etc/apache2/apache2.conf
RUN rm -f /munin.apache.conf

RUN mkdir /etc/service/apache2
ADD apache2.sh /etc/service/apache2/run
RUN chmod +x /etc/service/apache2/run

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]
