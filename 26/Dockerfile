FROM fedora:26

LABEL maintainer="Wilmar den Ouden <info@wilmardenouden.nl>"

ENV container docker

RUN dnf -y update \
    dnf install -y dnf-versionlock \
    && dnf versionlock systemd \
    && dnf clean all

COPY systemctl3.py /usr/bin/systemctl

CMD /usr/bin/systemctl