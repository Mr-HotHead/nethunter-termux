# nethunter-termux
***A guide on how to install Kali-Nethunter in your phone.***

**Update**: Ignore steps 7,8,9,10 and 11 as the present version installer has OS file with normal rootfs (Incase if you still run into the rootfs error, then follow steps 7, 8 ,9 ,10 and 11 too)

_(BTW sorry for the late update, I didn't check the installer and I didn't even replied to the issues opened. This update should fix most of the issues)_

## Pre-Requisties:

1)Android Phone(no need to be rooted)

2)Termux App(as you install nethunter in termux only)

3)_Minimum 8GB storage_

## Procedure:

1)**Download Termux app** from ~~playstore~~ **F-Droid**
>Termux app is available only for Android,so you need an Android phone

2)Open Termux and **type** `termux-setup-storage`
> So termux can access your internal storage

3)Now **type** `pkg install wget`
>wget tool helps in downloading files from internet in linux environment

4)Now **type** `wget -O install-nethunter-termux https://offs.ec/2MceZWr`
>The installer is now downloaded

5)Now **type** `chmod 777 install-nethunter-termux`
>Now you have the permission to run the installer

6)Now **type** `./install-nethunter-termux`
>The installer is now started 

7)Now the installer will download some tools and will *start downloading the Kali-Nethunter OS*,now **click on CTRL+X**,this will _stop the downloading_.
>The OS downloaded from this installer has its rootfs corrupted,so we stopped the download

8)Now **type** `cd` then `ls`,it will show you two files **kalifs-arm64-full.tar.xz** and **kalifs-arm64-full.tar.xz.st**,remove those files by typing `rm -rf kalifs-arm64-full.tar.xz` and `rm -rf kalifs-arm64-full.tar.xz.st`
>These files have the corrupted OS,so we don't need them

9)Now **go to** [The OS download page](https://images.kali.org/nethunter/kalifs-arm64-full.tar.xz),a 1.7GB file will be downloaded
>This is the Kali-Nethunter OS which doesn't have its rootfs corrupted

10)After the Download is finished,come back to Termux and **go to** the folder where the OS file is downloaded,now **move** the OS file to the home directory by **typing** `mv kalifs-arm64-full.tar.xz. /data/data/com.termux/files/home`
>We need to make sure the installer and the OS file are on same directory,for this case the installer is in the home directory so the OS file is moved to the home directory

11)Now type `cd` and run the installer by **typing** `./install-nethunter-termux`,it will say ***"Existing rootfs found,delete and download new one (Y/n)?"***, **type** _n_ and click enter.
>It is asking whether to delete the OS file we downloaded,as we need it to install nethunter we won't delete it.

12)It will show ***"extracting rootfs file"***,that means Kali-Nethunter is being installed.
>This will take from 30mins-1hour,so make sure you have enough battery in your phone.

13)After the extraction is finished, it will show ***"Delete the existing rootfs file?(Y/n)"***. Type _Y_ if you don't need the OS file as the installation is finished,or type _n_ if you want the OS file for future purposes.

14)Now Kali-Nethunter is successfully installed in our Android Device. It will show you some commands on how to access Nethunter

`nethunter` or `nh`(_to run the Command line version in termux_)

`nethunter -r` (_to run the Command Line version as root_)

`nethunter kex password` (_to set the password for the Nethunter GUI version_, **you need to set password if you want to run Nethunter GUI version**)

`nethunter kex &` (_to run the GUI version_)

15)To access the GUI version,you need ***Nethunter Kex app***, **download it** from **Nethunter-App store** from [store.nethunter.com](store.nethunter.com)
>We need Nethunter Kex app to access the Nethunter GUI version. You can download Nethunter Kex app from "Nethunter-App Store" app which you can download from the site listed above.

16) Once you have installed Nethunter Kex app, open termux and **type** `nethunter kex passwd` and set the password. After you set password **type** `nethuntex kex &`. It will show you a port number,copy that port number and open _Nethunter Kex App_ and paste the port number there(_beside the IP address,which is localhost_)

17)Then type the password up in the password field and **click** connect.

***NOW YOU ARE IN KALI NETHUNTER!!***


## Some Questions Related to Kali-Nethunter

1)**What is Kali-Nethunter?**
Ans:- _Kali-Nethunter is the mobile version of Kali Linux_

2)**How much space does Kali-Nethunter occupy in device storage?**
Ans:- _From 8GB to 10GB_

3)**Does Kali-Nethunter have same features and applications as Kali Linux?**
Ans:- _No. Kali-Nethunter has less features and applications than Kali Linux. You can't even connect to an openvpn config in Kali-Nethunter. Kali Linux is far more better than Kali-Nethunter in my opinion_.



