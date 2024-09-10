version: "3"
build:
  steps:
    - type: apt-get
      packages: ["wget", "unzip"]
    - type: command
      command: |
        wget https://storage.googleapis.com/dart-archive/channels/stable/release/3.4.3/sdk/dartsdk-linux-x64-release.zip
        unzip -d /usr/local/dart dartsdk-linux-x64-release.zip
        rm -rf dartsdk-linux-x64-release.zip
        echo 'export PATH=$PATH:/usr/local/dart/dart-sdk/bin' | tee -a /etc/profile.d/dart-installation.sh
        chmod +x /etc/profile.d/dart-installation.sh
      user: root
