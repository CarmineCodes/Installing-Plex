# How to install Plex Media Server on Linux

This writeup will cover how to install Plex Media Server on a Linux machine to self-host your own media server.

## Getting Started

To start, you can run Plex in many ways whether in a docker container, to off a nas, or how this will cover in a virtual machine off a server. This can also be a standalone box running a flavor of Linux. For this, I am going to use Ubuntu server 20.04 LTS.

For system requirements, Plex recommends at least an intel core i3, this varies by how many people you intend to use your server. I typically give my Vm’s 2 cores for plex.

For ram, at least 2 gb but this also will need to vary depending on how many users there will be.
I would advise to give the VM a drive of 50 gb and host the media off the machine in a nas or network drive.


### Prerequisites

Power your new (or old) Linux machine up and make sure is it all updated.

Run:

    sudo apt update

and

    sudo apt upgrade -y

After the machine is up to date, we are ready to install Plex.

### Installing

In your Linux machine, make a new directory for the plex installer.

    sudo mkdir PlexInstaller

then navigate to the official plex site and under download, find the latest version of Plex Server for Linux.

    https://www.plex.tv/media-server-downloads/#plex-media-server

From there, Select Linux, there will be a button for Choose Distro, click on that then a menu of flavors will open.

![image](https://user-images.githubusercontent.com/63487881/214430325-499dd4a0-6bcd-4e70-b1d1-c7ea1330c7b4.png)

![image](https://user-images.githubusercontent.com/63487881/214430380-6747df8c-798c-4b11-a119-9ce6f3a90caf.png)

Right click on the flavor of Linux you are running and click copy link in the menu that opens.


After grabbing the link to the latest version

change directories into the new directory and wget the link you copied.

    sudo wget paste the link.
 
 The output should like look this
 
 ![image](https://user-images.githubusercontent.com/63487881/214473479-6dfd956f-b654-4662-8af6-f7d548823680.png)

after getting the installer, we need to run the dpkg to install the plex server software onto our machine.

Replace "latestVersion" with the latest version id found on the plex download site. it should look similar to this.

![image](https://user-images.githubusercontent.com/63487881/214602507-e59eb931-f35a-435e-bbeb-11e2e512303b.png)

then add the latest version number to the command below in place of "latestVersion"

    sudo dpkg -i plexmediaserver_latestVersion_amd64.deb

dpkg will work to install the software and after it is done we are almost ready.

just in case, we are going to open the port on the machine for plex to reach out.

Plex uses port 32400 and we are going to open it with ufw.

Run the command.

    sudo ufw allow 32400
   
This will open the port on the machine to allow Plex traffic to head outbound.

If you get an error that ufw isn’t installed, run

    sudo apt install ufw

This will install ufw, after that run the command to open the port again and it will open it up.

## Updating Plex

When Plex releases new updates, you should read over the release notes and make sure it’s nothing to drastic and you feel comfortable installing the newest version. The easiest way to do this is to add the Plex repo to all the repos your machine uses when you update it. To do this run the command below.

    echo deb https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list

then

    curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add -

Now the plex repos are added so when you update your machine it will also update Plex.

So, when you run 

    sudo apt update
&
    sudo apt upgrade
    
Plex will automatically update as well.

### Accessing Plex

Now that Plex is installed you are ready to access it, to do so you will go to the IP address of the machine with port 32400.

    hostip:32400/web
    
 There you should see the welcome screen asking you to sign in or make an account.

After you make your account, plex is ready to be used, you can connect a drive of media however you'd like and start streaming.

### Resources

Plex Download
    
    https://www.plex.tv/media-server-downloads/#plex-media-server
    
Repos to update Plex.

    https://support.plex.tv/articles/235974187-enable-repository-updating-for-supported-linux-server-distributions/

Official Plex install guide

    https://support.plex.tv/articles/200288586-installation/
