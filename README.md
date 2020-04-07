# mt7610u-linksys-ae6000-wifidriver-fixes
Installation process for for the tp-link t2uh on linux server

To install(Working on Ubuntu server 18.04):

sudo apt install git
cd ~
git clone https://github.com/Crazy522/mt7610u-linksys-ae6000-wifidriver-fixes.git
cd mt7610u-linksys-ae6000-wifidriver-fixes

sudo apt-get install build-essential linux-headers-$(uname -r)
make clean
make
sudo make install

If you want the driver to work after the updating the kernel I advise to follow the next steps that includes the dkms utility. You will need to work in the directory "mt7610u-linksys-ae6000-wifi-fixes" otherwise the process will not work.
sudo apt-get install dkms  
sudo cp -R . /usr/src/mt7610u_sta-1.0
sudo dkms add mt7610u_sta/1.0
sudo dkms build mt7610u_sta/1.0
sudo dkms install mt7610u_sta/1.0



