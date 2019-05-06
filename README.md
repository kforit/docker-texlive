# docker-texlive

## Example Usage

```shell
# Keep the container running
docker run -itd --name texlive -v ~/workspace:/workspace kforit/texlive /bin/sh

# Change default repository
docker exec texlive tlmgr option repository http://mirror.ctan.org/systems/texlive/tlnet

# Upgrade to a complete TeXLive installation
docker exec texlive tlmgr install scheme-full
docker exec texlive tlmgr update --self --all

# Compile
docker exec texlive latexmk -xelatex main.tex

# Clean
docker exec texlive latexmk -c
```
