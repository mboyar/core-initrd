### Enabling the test envrionment

```
sudo su
mkdir -p /home/root/.spread/qemu
cd /home/root/.spread/qemu
wget https://spread.zygoon.pl/ubuntu-20.04-64.img.xz
unxz ubuntu-20.04-64.img.xz
exit
sudo apt update && sudo apt install -y qemu-kvm autopkgtest
cd $HOME  #or whereever you want
git clone https://github.com/mboyar/core-initrd.git
cd core-initrd
curl -vs https://storage.googleapis.com/snapd-spread-tests/spread/spread-amd64.tar.gz
sudo SPREAD_QEMU_BIOS=snakeoil/OVMF_VARS.snakeoil.fd ./spread -v qemu-nested:

```
*Note: The related helpful URL https://github.com/snapcore/snapd/blob/master/HACKING.md*

Test result can be seen below:

![Selection_078](https://user-images.githubusercontent.com/3090609/129152007-b663756c-cb91-4158-9fd9-920a68f74b81.jpg)
