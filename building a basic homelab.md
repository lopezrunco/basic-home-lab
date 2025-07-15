# Building a basic homelab

## 1. Download and install VirtualBox

Go to https://www.virtualbox.org/wiki/Downloads and click on Windows hosts.

![virtualbox-download-page.png](./assets/virtualbox-download-page.png)

While is downloading, go ahead and check out `SHA256 checksums` to check that the downloaded file wheter or not has been altered. To do that, go to the `Downloads` folder (or whatever is the folder where you downloaded the installer) open a PowerShell console and type:

```powershell
    Get-FileHash .\VirtualBox-7.1.10-169112-Win.exe  
```

This will return a SHA256 hash, we copy it, return to the `SHA256 checksums` page in the VirtualBox websaite and check if the hash matches some of the items of the list (Ctrl + F and paste the hash).

Now we know that the file in transit was not altered whatsoever. We can proceed with the installation of Virtual Box, just follow the instructions of the wizard and you should be fine.

## 2. Install Windows 10

Go to <a href="https://www.microsoft.com/en-ca/software-download/windows10">this link</a> and scroll to the `Create Windows 10 installation media` and click `Download now`. This will download a media creation tolls, which will help us create the Windows 10 image file.

Once we run the installer, on the part `What do you want to do?` screen, click on `Create installation media` and then select `ISO file`.

![Create installation media](./assets/create-installation-media.png)

After downloading the Windows 10 ISO file, we go to VirtualBox and create our first virtual machine.

Click on `New` and you will be prompted with a Create Virtual Machine wizard. We are naming this machine `windows10`, select the ISO image and check the box `Skip unattended installation`, that way we can install the operating system manually. 

Click on Next and we will see the virtual machine specifications.

![Install windows10](./assets/install-windows10.png)

Do notice that this will be relying on your computers specifications, here I will assign 2048 MB as Base Memory and 1 CPU in Processors.

![Windows 10 Virtual machine hardware](./assets/hardware.png)

On Virtual Hard Disk I will leave it at 50 GB and hit next.

![Windows 10 Virtual machine Virtual hard disk](./assets/virtual-hard-disk.png)

Then, the wizard will show you a summary of what your settings are for this virtual machine, if you are good to go, click on finish. 

To power on our windows 10 machine, just click `Start`. We should be able to see the Windows 10 setup screen.

![](./assets/windows-10-setup.png)

We click on Install and once you are presented with the Activate Windows screen, click on `I don't have a product key` and in the options select Windows 10 Pro. Click Next, accept the license terms.

In the next screen, select Custom install Windows only, select the drive and click Next and then Windows 10 should be installing in the background.

## 3. Install Kali Linux

First, navigate to the Kali website https://www.kali.org, click in download and then click on the `Pre-built VMs` menu item. I'll be downloading the 64-bit version of Kali but you should download the option in accordance with your system architecture.

![Download Kali Linux](./assets/download-kali.png)

A 7-zip file will be downloaded, so you will need 7-Zip in order to decompress the file. Once decompressed, look for the file with the `vbox` extension and doble click it. The Kali Linux should be automatically imported into Virtual Box.
Now you can start the Kali virtual machine. Note: The default credentials of the Kali Linux machine are `kali/kali`.

![Start Kali Linux](./assets/start-kali-linux.png)

## Important:

In order to prevent your host machine to get infected, first you need to properly configure the virtual machines.

