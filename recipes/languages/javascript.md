version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl", "unzip", "tar"]
    - type: command
      command: |
        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
        export NVM_DIR=$HOME/.nvm && [ -s $NVM_DIR/nvm.sh ] && \. $NVM_DIR/nvm.sh
        nvm install 21.0.0
        echo '. $HOME/.nvm/nvm.sh' >> $HOME/.bashrc
        echo '. $HOME/.nvm/nvm.sh' >> $HOME/.zshrc
        npm install --global yarn
