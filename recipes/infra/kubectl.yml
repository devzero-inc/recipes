version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl"]
    - type: command
      command: |
        curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
        sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
        rm kubectl
      user: devzero
