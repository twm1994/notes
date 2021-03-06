### Resize Window 
`sudo vim /etc/default/grub`

add following line 
`GRUB_GFXPAYLOAD_LINUX=1024x768x16`

`:wq` to save and quit
```sh
sudo update-grub
sudo shutdown -h now
```

### List Packages 
`apt list --installed|less`


### Conda 
`curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh`


### Share a Folder

this example mounts the Ubuntu_Server folder from host to /home/twm/shared in guest working directory is /home/twm

`sudo apt-get install virtualbox-guest-utils`

folder name in `Shared Folders option -> folder name` in guest machine

`sudo mount -t vboxsf Ubuntu_Server shared`

persistent mount 

`sudo vim /etc/fstab`

add following line (separated by tabs)

`Ubuntu_Server  /home/twm/shared vboxsf  defaults  0 0`

`:wq` to save and quit

permission
```sh
sudo usermod -aG vboxsf twm
sudo vim /etc/modules
```
add following line 
`vboxsf`

`:wq` to save and quit, then reboot

point apache's web directory to the shared folder
```sh
sudo rm -rf /var/www/html
sudo ln -s ~/shared /var/www/html
```


### Miscellaneous

edit open with application
```sh
sudo vim ~/.config/mimeapps.list
sudo vim ~/.local/share/applications/mimeapps.list
```

remove cloud-init
```sh
echo 'datasource_list: [ None ]' | sudo -s tee /etc/cloud/cloud.cfg.d/90_dpkg.cfg
sudo apt-get purge cloud-init
sudo rm -rf /etc/cloud/; sudo rm -rf /var/lib/cloud/
reboot
```

clean command history

`rm ~/.bash_history && history -c`

earch if there is an instance of apt command running

`ps aux | grep -i apt`

clean packages

`sudo apt-get autoremove`

in case locate does not work

`sudo updatedb`

for grub config

`sudo add-apt-repository ppa:danielrichter2007/grub-customizer`

thermal control
```sh
sudo add-apt-repository ppa:linrunner/tlp
sudo apt-get update
sudo apt-get install tlp tlp-rdw
sudo tlp start
sudo apt-get install indicator-cpufreq
```
sensor

```sh
sudo apt install lm-sensors hddtemp
sudo sensors-detect
sudo apt install psensor
```

change console setup

`vim /etc/default/console-setup`

fast update

`sudo sed -i -e 's/http:\/\/us.archive/mirror:\/\/mirrors/' -e 's/\/ubuntu\//\/mirrors.txt/' /etc/apt/sources.list`

### VirtualBox Guest Additions

`sudo apt install build-essential dkms linux-headers-$(uname -r)`

cd to the mount point of VBoxGuestAdditions.iso

`sh ./VBoxLinuxAdditions.run`

### Install TexLive

`sudo vi /etc/bash.bashrc`

add at the end of the file
```sh
PATH=/usr/local/texlive/bin/x86_64-linux:$PATH; export PATH
MANPATH=/usr/local/texlive/texmf-dist/doc/man:$MANPATH; export MANPATH
INFOPATH=/usr/local/texlive/texmf-dist/doc/info:$INFOPATH; export INFOPATH
```

save

`source ~/.bashrc`

### Chinese Input

`sudo apt install fcitx-bin fcitx-googlepinyin`
