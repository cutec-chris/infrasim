from alpine:edge
run apk add\
    podman\
    python3\
    py3-pip\
    bash\
    git\
    openssh\
    openssh-server-pam\
    linux-pam
run pip3 install podman-compose 
run ln -s $(which podman) /usr/bin/docker
run ln -s $(which podman-compose) /usr/bin/docker-compose
run rm -rf /tmp/* /var/cache/apk/*
run ssh-keygen -A
EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]