FROM debian

ARG TL_ISO=https://lite.kgt.app/rd/tl2019iso

WORKDIR /texlive_install

COPY texlive.profile .

RUN apt update && apt install -y wget curl perl-tk  p7zip-full \
 && wget -qO texlive.iso $TL_ISO \
 && 7z x texlive.iso > /dev/null \
 && rm -f texlive.iso \
 && chmod +x ./install-tl \
 && ./install-tl -profile texlive.profile \
 && rm -rf ./*

WORKDIR /workspace
