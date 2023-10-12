FROM ubuntu:20.04

RUN apt-get update && apt-get install -y

RUN apt-get install openssh-server -y

# CREATE USER
RUN useradd remote_user -m
RUN usermod --password "12345" remote_user
RUN chown -R remote_user:remote_user /home/remote_user

# SSH CONFIGURATION
RUN mkdir /home/remote_user/.ssh
RUN mkdir /var/run/sshd

COPY keys/jenkins.pub /home/remote_user/.ssh

RUN cat /home/remote_user/.ssh/jenkins.pub > /home/remote_user/.ssh/authorized_keys
RUN chown -R remote_user:remote_user /home/remote_user/.ssh
RUN chmod 600 /home/remote_user/.ssh/authorized_keys

# TURN OFF SSH PASSWORD LOGIN
RUN sed -i 's/#PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config

EXPOSE 22

# START SSH SERVER
CMD ["/usr/sbin/sshd", "-D"]
