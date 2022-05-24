from alpine:edge
run apk add\
    podman\
    python3\
    py3-pip\
    py3-paramiko\
    bash\
    git\
    openssh
run pip3 install podman-compose 
run ln -s $(which podman) /usr/bin/docker
run ln -s $(which podman-compose) /usr/bin/docker-compose
add sshd.py .
cmd ["sshd.py"]
entrypoint ["python3"]