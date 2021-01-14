# base image
FROM ubuntu:18.04

# SSH Setting
RUN apt-get update && apt-get install -y openssh-server

# make directory to start sshd process.
RUN mkdir /var/run/sshd

# change root user can login.
# sed -i `s/before/after
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# Explicitly allow password authentication.
RUN sed -i 's/#PasswordAuthentication/PasswordAuthentication/' /etc/ssh/sshd_config

# Change password of root user in container to ssh login. 
RUN echo 'root:root' | chpasswd

# EXPOSE command means open port
EXPOSE 22

# When this option is specified, sshd will not detach and does not become a daemon.
# This allows easy monitoring of sshd.
CMD ["/usr/sbin/sshd", "-D"]
# END