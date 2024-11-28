This lab will teach you how to perform basic software maintenance on Linux machines. This includes installing software that's not already present on the machines, updating existing software to the newest version, and uninstalling software that‘s no longer needed. All of these tasks are very common in the IT world, so it's important that you're able to do them quickly and effectively.

<h2>There are three learning objectives for this lab:</h2>

<p align="center">

 - Update- The machine you'll be using comes preinstalled with an old version of the VLC Media Player. You'll update VLC to the newest version.
 - Install- You'll install the Mozilla Firefox web browser. There's currently no version of Firefox on the machine you'll be using, so it will be a fresh installation.
 - Uninstall - You'll uninstall the GIMP photo-editing tool from the machine, removing it entirely.

<p align="center">
<h2>Verifying installed software on Linux</h2>
To quickly check if a program is installed on Linux, you can use the command "dpkg -s" followed by the unique package name for that program. The "-s" flag in dpkg stands for "search," which allows you to search for a program on your machine and check if it's installed. For example, we know that Firefox isn't currently installed, but GIMP is. Running "dpkg -s firefox-esr" shows this output:


<p align="center">
<img src="https://i.imgur.com/2NeRzve.png"/>

<p align="center">
This shows you that Firefox isn't currently installed on the system. To check GIMP, modify the earlier command and enter "dpkg -s gimp" to see the output below. (Note that only part of the output is shown.)

<img src="https://i.imgur.com/uQxDMhN.png"/>

<p align="center">
You can see that the status of gimp is "installed". As long as you know the package name, you can use "dpkg" to check the status of any program.
<p align="center">
Running "dpkg -s vlc" shows you that vlc is installed, but also that the version is out-of-date. (Version 2.2.7 is installed, but the newest version is at least 3.0.12)
<p align="center">
<img src="https://i.imgur.com/4hgQIgj.png"/>
<p align="center">
<h2>Updating VLC Media Player</h2>

<p align="center">
VLC media player is already installed on your computer, but the version that's installed is out-of-date. You'll fix that now by updating it to the newest version. To do that, force an update of the package manager, using this command:

<p align="center">
sudo apt-get install -f
<p align="center">
This kicks off the update process. It will print out lots of text to your terminal, and ask you if you'd like to continue. Enter "y" for "yes". When the process is finished, type "dpkg -s vlc" again to verify the installation.
<p align="center">
<img src="https://i.imgur.com/veODVun.png"/>
<p align="center">
You can see here that VLC has been updated to a newer version (3.0.12 was the newest at the time this screenshot was taken). Your version should be at least 3.0.12, but could be higher if newer versions have been released.

<h2>Installing Mozilla Firefox</h2>
<p align="center">
Let's install the Mozilla Firefox web browser. Parts of this process will be unique to this specific installation, but most of the steps you'll take will be identical, regardless of the software.
<p align="center">
Lots of common programs, including Firefox, are set up in repositories that most Linux distributions are aware of, by default. This makes installing these programs super easy, and allows you to bypass having to manually download and install the program. To make sure these repositories are up-to-date and all dependencies are fixed, run the below command into the terminal (you will have to enter the letter "Y" at some point during the process to confirm your action):
<p align="center">
sudo apt-get update
<p align="center">
This will start the repository update process, which should look something like this when it's finished:
<p align="center">
<img src="https://i.imgur.com/lLb4plo.png"/>
<p align="center">
Now you're ready to install Firefox. Run the below command in the terminal:
<p align="center">
sudo apt-get install firefox-esr
<p align="center">
You'll be prompted to confirm that you‘d like to continue with the installation. To continue, enter "y" (as in "yes") into the terminal, and hit "enter". For future reference, to cancel the installation process, you'd just enter anything other than "y".
<p align="center">
<img src="https://i.imgur.com/oRz25c1.png"/>
<p align="center">
After confirming the installation, the terminal will briefly fill with lines of text. Once this process is complete, Firefox will be installed on your instance. To verify that it's installed, enter "dpkg -s firefox-esr" into the terminal window again, and you'll see different output than before:
<p align="center">
<img src="https://i.imgur.com/2pLRS0T.png"/>
<p align="center">
You can see that the status is listed as "installed", meaning that the process was successfully completed. Wohoo! Now you can move onto updating software.

<h2>Uninstalling Gimp</h2>
<p align="center">
When it's no longer necessary to have a specific program installed on your computer, it's usually a good idea to uninstall it to clear up space. Now, you'll uninstall the GIMP photo-editing software, removing it from the computer completely.
<p align="center">
GIMP, like Firefox, can be installed and uninstalled using the "apt-get" commands that you used to install Firefox. To uninstall GIMP, a very similar command is used:
<p align="center">
sudo apt-get remove gimp
<p align="center">
This command will kick off the process of uninstalling GIMP from your instance. Shortly after starting, it will prompt you to confirm the uninstallation. Enter "y" to confirm, and the process will begin:
<p align="center">
<img src="https://i.imgur.com/w9ZwZcB.png"/>
<p align="center">
After receiving your confirmation, the process will continue and GIMP will be uninstalled. You can verify that the process was successful by running the same command we used to verify its installation ("dpkg -s gimp"). You'll receive the following message. (Only part of the message is shown below.) Note the this message shows that GIMP has been "deinstalled".
<p align="center">
dpkg -s gimp
<p align="center">
<img src="https://i.imgur.com/5w8Y7mg.png"/>
<p align="center">
This confirms that GIMP was successfully removed from your computer.
<p align="center">
<h2>Congratulations!</h2>
<p align="center">
You've successfully installed Firefox, updated VLC, and uninstalled GIMP on a Linux machine.







