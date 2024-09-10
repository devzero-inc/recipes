version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl"]
    - type: command
      command: |
        wget https://gitlab.com/gitlab-org/cli/-/releases/v1.41.0/downloads/glab_1.41.0_Linux_x86_64.deb
        sudo dpkg -i glab_1.41.0_Linux_x86_64.deb
      user: devzero
