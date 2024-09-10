version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl", "gnupg", "software-properties-common", "terraform"]
      extra_repositories:
      - key_url: https://apt.releases.hashicorp.com/gpg
        repository: https://apt.releases.hashicorp.com
        components: ["main"]
