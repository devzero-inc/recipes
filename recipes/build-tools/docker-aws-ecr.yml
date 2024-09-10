version: "3"
build:
  steps:
    - type: apt-get
      packages: ["wget"]
    - type: command
      command: |
        VERSION=0.8.0
        wget https://amazon-ecr-credential-helper-releases.s3.us-east-2.amazonaws.com/$VERSION/linux-amd64/docker-credential-ecr-login
        chmod +x docker-credential-ecr-login
        sudo mv docker-credential-ecr-login /usr/local/bin
