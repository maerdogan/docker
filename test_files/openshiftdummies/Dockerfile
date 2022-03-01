FROM alpintosh/ubuntu:v3


# ubuntu:latest does not have sudo
# fetch it and install it
RUN apt-get update && apt-get install -y sudo

# Create new user `docker` and disable 
# password and gecos for later
# --gecos explained well here:
# https://askubuntu.com/a/1195288/635348
RUN adduser --disabled-password \
--gecos '' docker

#  Add new user docker to sudo group
RUN adduser docker sudo

# Ensure sudo group users are not 
# asked for a password when using 
# sudo command by ammending sudoers file
RUN echo '%docker ALL=(ALL) NOPASSWD:/usr/bin/dockerd' >> \
/etc/sudoers

# now we can set USER to the 
# user we just created
USER docker

# we can now run sudo commands 
# as non-root user `docker` without
# password prompt
RUN sudo apt-get update 

WORKDIR /home/docker/src

COPY . .

CMD tail -f /dev/null
