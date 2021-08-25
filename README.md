# Vagrant-Scripts

This Repo contains Prebuilt Vagrant files for initializing specific VM's.

The first file named is Vagrantfile and can be used as it is to initiliaze two machines with Ubuntu Bionic. One as a web server and another one as a database. The internal configurations can be changed by editing the variables. The script is designed for use with OracleBox, but for VMware one can also modify line 13 and 36. Memory size, hostname and networking configurations can also be edited based on requirement.

The second file is used for deploying a simple centos 7 machine. However to use it via vagrant up command it must be renamed to Vagrantfile and stored in a separate directory from the first file
