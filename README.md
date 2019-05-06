# docker-texlive

This image only contains the infrastructure. Use `tlmgr install ...` to install packages as you need.

## Example Usage

```shell
# Get and mount the texlive iso file for easier installation
sudo mkdir -p /mnt/texlive
sudo mount -o loop texlive.iso /mnt/texlive

# Keep the container running
docker run -itd --name texlive -v ~/workspace:/workspace:rw -v /mnt/texlive:/mnt/texlive:ro kforit/texlive /bin/sh

# Change default repository
docker exec texlive tlmgr option repository /mnt/texlive
docker exec texlive tlmgr option repository http://mirror.ctan.org/systems/texlive/tlnet

# Upgrade to a complete TeXLive installation
docker exec texlive tlmgr install scheme-full
docker exec texlive tlmgr update --self --all

# Compile
docker exec texlive latexmk -xelatex main.tex

# Clean
docker exec texlive latexmk -c
```
