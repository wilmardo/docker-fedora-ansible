FROM fedora:27

LABEL maintainer="Wilmar den Ouden <info@wilmardenouden.nl>"

ENV container docker

# We only want few core services run in the container.
RUN systemctl mask \
        dev-hugepages.mount \
        sys-fs-fuse-connections.mount \
        sys-kernel-config.mount \
        display-manager.service \
        getty@.service \
        systemd-logind.service \
        systemd-remount-fs.service \
        getty.target \
        graphical.target \
        console-getty.service \
        systemd-vconsole-setup.service \
        kmod-static-nodes.service \
    && systemctl set-default multi-user.target

STOPSIGNAL SIGRTMIN+3

ENTRYPOINT ["/sbin/init"]
