.PHONY: clean-vm clean-vagrant-metadata

all: test

test: test-boot test-compile test-pip

test-boot:
	vagrant up

test-compile: test-boot
	vagrant ssh -c "cd /vagrant && python3 hello.py"

test-pip: test-boot
	vagrant ssh -c "sudo pip3 install bashate && which bashate"

clean-vm:
	-vagrant destroy -f

clean-vagrant-metadata:
	-rm -rf .vagrant

clean: clean-vm clean-vagrant-metadata
