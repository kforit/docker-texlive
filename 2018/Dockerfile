FROM alpine

ARG TL_ISO=ftp://tug.org/texlive/historic/2018/texlive2018.iso
ARG TL_REPOSITORY=ftp://tug.org/historic/systems/texlive/2018/tlnet-final

WORKDIR /texlive_install

COPY texlive.profile .

RUN apk add --no-cache -U -u wget p7zip perl \
 && wget -qO texlive.iso $TL_ISO \
 && 7z x texlive.iso > /dev/null \
 && rm -f texlive.iso \
 && chmod +x ./install-tl \
 && ./install-tl -profile texlive.profile \
 && rm -rf ./* \
 && tlmgr option repository $TL_REPOSITORY

WORKDIR /workspace
