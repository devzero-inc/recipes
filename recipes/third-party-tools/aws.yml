version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl"]
    - type: command
      command: |
        sudo apt-get update && sudo apt-get upgrade -y && sudo apt-get install -y curl unzip
        curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
        unzip awscliv2.zip
        sudo ./aws/install
        rm -rf aws awscliv2.zip
