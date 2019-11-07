FROM debian

ENV TL_ISO=https://mirrors.aliyun.com/CTAN/systems/texlive/Images/texlive2019.iso

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
