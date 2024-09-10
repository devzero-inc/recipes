version: "3"
build:
  steps:
    - type: apt-get
      packages: ["libpq-dev", "libpython3.8-dev", "python3.8", "python3.8-venv", "software-properties-common"]
      extra_repositories:
      - repository: ppa:deadsnakes/ppa
    - type: command
      command: |
        python3.8 -m venv venv
        . venv/bin/activate
        curl https://bootstrap.pypa.io/get-pip.py --output get-pip.py
        python get-pip.py
        rm get-pip.py
      directory: /home/devzero
    - type: command
      command: |
        python3.8 -m venv venv
        echo "source /home/devzero/venv/bin/activate" >> /home/devzero/.bashrc