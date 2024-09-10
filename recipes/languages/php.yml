version: "3"
build:
  steps:
    - type: apt-get
      packages: ["build-essential", "curl", "git", "nano", "software-properties-common", "ssh", "sudo", "tar", "unzip", "vim", "wget", "zip"]
    - type: command
      command: |
        sudo apt update
        sudo apt upgrade -y
        DEBIAN_FRONTEND=noninteractive DEBCONF_NONINTERACTIVE_SEEN=true TZ=Etc/UTC sudo -E apt install php -y
        sudo apt install php-mysql php-curl php-json php-cgi php-cli php-xml php-gd php-mbstring php-zip -y
        sudo apt install libapache2-mod-php -y
      directory: /home/devzero
      user: devzero
