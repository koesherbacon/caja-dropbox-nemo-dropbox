### Caja-Dropbox & Nemo-Dropbox for ArchLinux ###
<br>


I used DebTap (abailable [here](https://github.com/helixarch/debtap) and [here](https://aur.archlinux.org/packages/debtap/)) to convert 
`caja-dropbox_1.18.0-1+sonya_amd64.deb` & `nemo-dropbox_3.4.0+sonya_amd64.deb` from [LinuxMint Sonya v18.2](https://www.linuxmint.com/download.php) into ArchLinux `*.tar.xz` installation packages because their AUR counterparts were not installable due to errors.
<br>

Please be aware that I did not create the actual packages from LinuxMint and will not mantain these vertions because the autors of the AUR's versions will surely fix the errors I enountered.  In the meantime, however, anybody is more than welcome to download and install `Nemo-Dropbox` and `Caja-Dropbox` with these converted versions in the meantime.
<br>

If you want to download and convert these packages yourself, follow these steps (not, I use ';' bc my shell of choice if fish.  but you can substitute '&&' for ';' if you want).

    yaourt -Sy debtap ; sudo debtap -u
    mkdir -m 777 ~/Downloads/debtap-conversions
    cd ~/Downloads/debtap-conversions
    wget -c http://mirror.metrocast.net/linuxmint-packages/pool/backport/c/caja-dropbox/caja-dropbox_1.18.0-1+sonya_amd64.deb http://mirror.metrocast.net/linuxmint-packages/pool/backport/n/nemo-dropbox/nemo-dropbox_3.4.0+sonya_amd64.deb
    debtap caja-dropbox_1.18.0-1+sonya_amd64.deb  nemo-dropbox_3.4.0+sonya_amd64.deb
<br>

Debtap takes a little while to convert the files, and it asks you what you want them to be named as well as which license you'd like to use.  Technically, you don't need to enter anything when prompted, but if you want to, go ahead and enter...
	
    caja-dropbox_1.18.0-1+sonya_amd64.deb 
    GPL
    nemo-dropbox_3.4.0+sonya_amd64.deb
    GPL
<br>

Once they have finished converting, install them with these commands:

    sudo chmod -Rv 777 *
    yaourt -U caja-dropbox-1.18.0-1-x86_64.pkg.tar.xz nemo-dropbox-3.4.0.sonya-1-x86_64.pkg.tar.xz --noconfirm --needed --force
<br> 

If for some strange reason the above command doesn't work, you can also simply navigate your file manager to `~/Downloads/debtap-conversions` and double click the newly created `caja-dropbox-1.18.0-1-x86_64.pkg.tar.xz` and `nemo-dropbox-3.4.0.sonya-1-x86_64.pkg.tar.xz` files.  A dialogue box should appear as Arch asks you if you want to install the packages.  Tell Arch you do indeed want to install, and they should both work fine afterward.
<br>

If you want to copy and paste everything above into your terminal as one long command, here it is (but you'll still have to enter the package names and license in the middle... or just keep hitting <kbd>enter</kbd>):

    yaourt -Sy debtap ; sudo debtap -u ; mkdir -m 777 ~/Downloads/debtap-conversions ; cd ~/Downloads/debtap-conversions ; wget -c http://mirror.metrocast.net/linuxmint-packages/pool/backport/c/caja-dropbox/caja-dropbox_1.18.0-1+sonya_amd64.deb http://mirror.metrocast.net/linuxmint-packages/pool/backport/n/nemo-dropbox/nemo-dropbox_3.4.0+sonya_amd64.deb ; debtap caja-dropbox_1.18.0-1+sonya_amd64.deb  nemo-dropbox_3.4.0+sonya_amd64.deb ; sudo chmod -Rv 777 * ; yaourt -U caja-dropbox-1.18.0-1-x86_64.pkg.tar.xz nemo-dropbox-3.4.0.sonya-1-x86_64.pkg.tar.xz --noconfirm --needed --force
<br>

This method should work for just about every other `.deb` package.  There will be some that won't work, but you can't blame me for that! 
<br>

You shouldn't encounter any problems, but if you do, please let me know and I'll try to help you out.
<br><br>

 ~ Ev

