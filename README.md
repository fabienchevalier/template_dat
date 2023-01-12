# Maleo's DAT

```bash
#Install dependencies
brew install --cask mactex

# update tlmgr and packages
sudo tlmgr update --self

# make python venv and install pandoc
conda create -n phd -y python=3.7 pandoc
conda activate phd

# Install required python and texlive packages
make install
./build.sh
```
