gbevan/vagrant-ubuntu-dev
-------------------------

Docker image of Ubuntu with build-essentials etc for development.  For use with Vagrant as a package build environment for the PasTmon project.

    VAGRANTFILE_API_VERSION = "2"
    Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
        config.vm.define "ubuntu-dev", primary: true do |ubuntu|
            ubuntu.vm.synced_folder "/", "/home/vagrant/src"
            ubuntu.vm.provider "docker" do |d|
                d.image = "gbevan/vagrant-ubuntu-dev:latest"
                d.has_ssh = true
            end
        end
    end
