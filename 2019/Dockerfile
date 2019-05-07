FROM alpine

# ARG TL_ISO=http://mirror.ctan.org/systems/texlive/Images/Images/texlive2019.iso
ARG TL_ISO=https://tug.org/texlive/Images/texlive2019.iso

WORKDIR /texlive_install

COPY texlive.profile .

RUN apk add --no-cache -U -u wget p7zip perl build-base \
 && wget -qO texlive.iso $TL_ISO \
 && 7z x texlive.iso > /dev/null \
 && rm -f texlive.iso \
 && chmod +x ./install-tl \
 && ./install-tl -profile texlive.profile \
 && rm -rf ./*

WORKDIR /workspace
