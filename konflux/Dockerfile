FROM registry.redhat.io/ubi9/ubi-init@sha256:5e25c1ed0c669e3a93dd82e0cbcdf7e663d9681a512278ec28d76675609cefaa

RUN subscription-manager register --org "$(cat /activation-key/org)" --activationkey "$(cat /activation-key/activationkey)"

RUN dnf install -y \
cpio systemd-ukify jq openssl qemu-img libguestfs guestfs-tools libguestfs-tools virt-install qemu-kvm edk2-ovmf nc

COPY qemu.conf /etc/libvirt/qemu.conf

# to make virt-customize work
ENV LIBGUESTFS_BACKEND=direct

