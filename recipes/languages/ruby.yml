version: "3"
build:
  steps:
    - type: apt-get
      packages: ["autoconf", "build-essential", "curl", "git", "libdb-dev", "libffi-dev", "libgdbm-dev", "libmysqlclient-dev", "libncurses5-dev", "libpq-dev", "libreadline6-dev", "libsqlite3-dev", "libssl-dev", "libxml2-dev", "libxslt1-dev", "libyaml-dev", "patch", "procps", "tar", "unzip", "zlib1g-dev"]
    - type: command
      command: |
        curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
        eval "$(~/.rbenv/bin/rbenv init - bash)" && export PATH="$HOME/.rbenv/bin:$PATH"
        rbenv install 3.3.1
        rbenv global 3.3.1
        echo 'eval "$(~/.rbenv/bin/rbenv init - bash)"' | sudo tee /etc/profile.d/ruby-installation.sh
        echo 'export PATH="$HOME/.rbenv/bin:$PATH"' | sudo tee -a /etc/profile.d/ruby-installation.sh
        sudo chmod +x /etc/profile.d/ruby-installation.sh
