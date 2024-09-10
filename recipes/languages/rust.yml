version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl", "libssl-dev", "pkg-config"]
    - type: command
      command: |
        curl -sSf https://sh.rustup.rs | sh -s -- -y
        . $HOME/.cargo/env
        rustup install 1.80.0
        rustup default 1.80.0
