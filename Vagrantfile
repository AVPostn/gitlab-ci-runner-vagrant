Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.provision "shell", env: {"TOKEN" => ENV['TOKEN']}, inline: <<-SHELL 
   apt-get update
   sudo snap install docker
   curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
   sudo apt-get install gitlab-runner
   sudo gitlab-runner register --non-interactive --url "https://gitlab.com/" --registration-token $TOKEN --executor "docker" --docker-image alpine:latest --description "docker-runner" --maintenance-note "Free-form maintainer notes about this runner" --tag-list "docker,aws" --run-untagged="true" --locked="false" --access-level="not_protected"
   sudo gitlab-runner register --non-interactive --url "https://gitlab.com/" --registration-token $TOKEN --executor "shell" --description "shell-runner" --maintenance-note "Free-form maintainer notes about this runner" --tag-list "docker,aws" --run-untagged="true" --locked="false" --access-level="not_protected"
  SHELL
end
