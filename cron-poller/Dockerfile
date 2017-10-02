FROM phusion/baseimage:0.9.22

RUN apt-get update --fix-missing
RUN apt-get install -y munin telnet

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN mkdir -p /munin/lib/munin && mkdir -p /munin/cache/munin/www && mkdir -p /munin/log/munin && mkdir -p /munin/run/munin
RUN chown -R munin:munin /munin
VOLUME /munin

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]
