version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl"]
    - type: command
      command: |-
        curl -fsSL https://get.pulumi.com | sh
        echo 'export PATH=$PATH:/home/devzero/.pulumi/bin' | sudo tee /etc/profile.d/151-pulumi-installation.sh
      user: devzero
