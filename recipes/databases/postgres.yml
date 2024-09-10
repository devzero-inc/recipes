version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl", "tar", "unzip"]
    - type: apt-get
      name: "postgres tools"
      packages: ["postgresql-16"]
      extra_repositories:
      - key_url: https://www.postgresql.org/media/keys/ACCC4CF8.asc
        repository: http://apt.postgresql.org/pub/repos/apt
        distribution: jammy-pgdg
        components: ["main"]
    - type: command
      command: |
        echo 'postgres     ALL=NOPASSWD: ALL' | sudo tee /etc/sudoers.d/100-postgres
        # Modify pg_hba.conf to allow trust authentication for devzero
        echo "local   all             devzero                                trust" | sudo tee -a /etc/postgresql/16/main/pg_hba.conf
        echo "host    all             devzero        127.0.0.1/32            trust" | sudo tee -a /etc/postgresql/16/main/pg_hba.conf
        echo "host    all             devzero        ::1/128                 trust" | sudo tee -a /etc/postgresql/16/main/pg_hba.conf
      directory: /home/devzero
      user: root
launch:
  steps:
    - type: command
      command: |
        # create the devzero user
        sudo -u postgres bash -c "psql -c \"CREATE USER devzero;\""
        # create a devzero database
        sudo -u postgres createdb devzero -O devzero
      user: root
