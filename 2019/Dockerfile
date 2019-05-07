FROM alpine

ARG TL_ISO=http://mirror.ctan.org/systems/texlive/Images/Images/texlive2019.iso

WORKDIR /texlive_install

COPY texlive.profile .

RUN apk add --no-cache -U -u wget p7zip perl \
 && wget -O texlive.iso $TL_ISO \
 && 7z -x texlive.iso \
 && rm -f texlive.iso \
 && ./install-tl -profile texlive.profile \
 && rm -rf ./*

WORKDIR /workspace
