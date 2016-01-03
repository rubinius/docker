all: rbxbuild buildimage

rbxbuild:
	wget https://rubinius-binaries-rubinius-com.s3-us-west-2.amazonaws.com/ubuntu/14.04/x86_64/rubinius-3.0.tar.bz2 -O rubinius.tar.bz2
	tar xvjf rubinius.tar.bz2
	rm rubinius.tar.bz2

buildimage:
	docker build --tag=rubinius-3.0-on-trusty .

clean:
	rm -rf .rbx/ rubinius/
