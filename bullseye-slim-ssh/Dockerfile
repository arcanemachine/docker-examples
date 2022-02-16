# syntax=docker/dockerfile:1

FROM arcanemachine/bullseye-slim-user

# copied from: https://adamtheautomator.com/ssh-into-docker-container/
# USER root
# RUN apt-get update && apt-get install -y openssh-server
# RUN mkdir /var/run/sshd
# RUN echo 'root:pass' | chpasswd
# RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
# RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd
# EXPOSE 22
# CMD ["/usr/sbin/sshd", "-D"]


# install and start the ssh server
USER root
RUN apt-get update\
    && apt-get install openssh-server -y\
    && service ssh start

# expose port 22 for ssh
EXPOSE 22

# # work as unprivileged user
USER user
WORKDIR /home/user

# create ssh config folder for user, with proper permissions
RUN mkdir .ssh && chmod 700 .ssh

# copy public key to 'authorized_keys' file and set proper permissions
COPY id_rsa.pub /home/user/.ssh/authorized_keys
RUN sudo chown user:user .ssh/authorized_keys\
    && chmod 600 .ssh/authorized_keys
