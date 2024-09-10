version: "3"
build:
  steps:
    - type: apt-get
      packages: ["build-essential", "curl", "git", "nano", "software-properties-common", "ssh", "sudo", "tar", "unzip", "vim", "wget", "zip"]
    - type: command
      command: |
        curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
        sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl && rm kubectl
      directory: /home/devzero
      user: devzero
    - type: command
      command: |
        curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
        chmod 700 get_helm.sh
        ./get_helm.sh
        rm get_helm.sh
      user: devzero

launch:
  steps:
    - type: command
      command: |
        helm install \
          -n bazel-buildfarm \
          --create-namespace \
          bazel-buildfarm \
          oci://ghcr.io/bazelbuild/buildfarm \
          --version "0.2.4"
    - type: command
      command: |
        kubectl port-forward service/bazel-buildfarm-server -n bazel-buildfarm 8980:8980 --address 0.0.0.0 &
