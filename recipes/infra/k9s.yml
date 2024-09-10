version: "3"
build:
  steps:
    - type: apt-get
      packages: ["wget"]
    - type: command
      command: |
        VERSION=v0.32.5
        wget https://github.com/derailed/k9s/releases/download/$VERSION/k9s_Linux_amd64.tar.gz
        mkdir k9s_Linux_amd64
        tar -xvf k9s_Linux_amd64.tar.gz -C k9s_Linux_amd64
        sudo mv k9s_Linux_amd64/k9s /usr/local/bin/
        rm -rf k9s_Linux_amd64*
