FROM alpine

ARG TL_REPOSITORY=ftp://tug.org/historic/systems/texlive/2018/tlnet-final

WORKDIR /texlive_install

COPY texlive.profile .

RUN apk add --no-cache -U -u wget tar gzip perl \
 && wget -O install-tl-unx.tar.gz $TL_REPOSITORY/install-tl-unx.tar.gz \
 && tar -xzf install-tl-unx.tar.gz \
 && rm -f install-tl-unx.tar.gz \
 && ./install-tl-*/install-tl -repository $TL_REPOSITORY -profile texlive.profile \
 && rm -rf ./*

WORKDIR /workspace
