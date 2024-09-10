version: "3"
build:
  steps:
    - type: apt-get
      packages: ["git"]
    - type: command
      command: |
        git clone https://github.com/ahmetb/kubectx /usr/local/src
        ln -s /usr/local/src/kubectx /usr/local/bin/kubectx
        ln -s /usr/local/src/kubens /usr/local/bin/kubens
        chmod +x /usr/local/bin/kubectx
        chmod +x /usr/local/bin/kubens
      user: root
