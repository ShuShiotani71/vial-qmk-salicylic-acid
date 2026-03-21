# best to fix it so that nothing breaks
FROM ghcr.io/qmk/qmk_cli@sha256:c6262b0a0a37e39a3688e582b509bc9f18289033d379b02dc194ed97f8c5a006

WORKDIR /root/

RUN apt update && apt install -y\
    vim\
    usbutils\
    openssh-client\
    tmux\
    tree

# use dotfiles and devcoontainer built in support for this rather than writing in dockerfile
# COPY my_config/* /root/

RUN git clone https://github.com/ShuShiotani71/vial-qmk-salicylic-acid.git --depth 1 --recurse-submodules --shallow-submodules qmk

WORKDIR /root/qmk

RUN python3 -m pip install -r requirements.txt
ENV USER=root

# some aliases; will put inside another file.
# make SKIP_GIT=yes salicylic_acid3/goforty_ortho:shiotani
# docker cp <container>:<path/to/file> <path/to/destination> # for uf2 file
#docker cp magical_mclean:root/qmk/.build/salicylic_acid3_goforty_ortho_shiotani.uf2 ~/Downloads


