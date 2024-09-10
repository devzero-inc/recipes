version: "3"
build:
  steps:
    - type: apt-get
      packages: ["wget"]
    - type: command
      command: |
        # detect architecture
        ARCH=$(uname -m)
        if [ "$ARCH" == "x86_64" ]; then
            GO_ARCH="amd64"
        elif [ "$ARCH" == "aarch64" ]; then
            GO_ARCH="arm64"
        else
            echo "Unsupported architecture: $ARCH"
            exit 1
        fi

        GO_VERSION="1.22.2"
        # download and install Go
        wget https://go.dev/dl/go${GO_VERSION}.linux-${GO_ARCH}.tar.gz
        tar -C /usr/local -xzf go${GO_VERSION}.linux-${GO_ARCH}.tar.gz
        rm -rf go${GO_VERSION}.linux-${GO_ARCH}.tar.gz

        # environment variables for DX
        echo 'export GOPATH=/home/devzero/go' | tee /etc/profile.d/go-installation.sh
        echo 'export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin' | tee -a /etc/profile.d/go-installation.sh
      user: root
