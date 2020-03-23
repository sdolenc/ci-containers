FROM linuxkit/dm-crypt:v0.7

#RUN pacman -Sy curl

RUN git clone https://aur.archlinux.org/snapd.git
RUN cd snapd
RUN makepkg -si
RUN systemctl enable --now snapd.socket
RUN ln -s /var/lib/snapd/snap /snap
RUN snap install curl-ijohnson
