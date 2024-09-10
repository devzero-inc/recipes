version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl"]
    - type: command
      command: |
        curl -Lo skaffold https://storage.googleapis.com/skaffold/releases/latest/skaffold-linux-amd64 && \
        sudo install skaffold /usr/local/bin/
        rm skaffold
      user: devzero
