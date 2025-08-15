
Logging into the UCT HPC
========================




Once you have been granted an account you will need to login to the head node of one of the clusters. All the clusters run Linux and you will need to be comfortable working with the command prompt. If you have had no experience with the Linux command line interface we have training material as well as a how to guide. Alternately there are numerous web articles on how to use the Linux command prompt.

Our head node is called hpc.uct.ac.za as well as hex.uct.ac.za.  When using these guides we refer to hpc.uct.ac.za, however you can substitute hex for hpc if you wish.

I have a Windows computer:
--------------------------
Logging in

You will need to download a ssh client. We recommend PuTTY from http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html.

We recommend just downloading the 64-bit x86 executable:



Save putty.exe to your C: drive and run it. Enter the hostname of the cluster, for example hpc.uct.ac.za, and click Open. The first time you do this answer Yes to the security alert.

  putty2

Now enter your username, press enter, then enter your password and press enter.  NB, the password characters will not appear when you type them, this is a security feature. You are now logged in. Type ls -l and press enter.

putty3   putty4

Here we see a folder called bin and a file called example.sh. To navigate to the bin folder enter cd bin. To move back again enter cd ..
To exit from the cluster type exit. It is beyond the scope of this document to discuss editing files or submitting jobs.

Transferring files

If you are comfortable using the windows command prompt, CMD, then you can download pscp.exe from http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html. To transfer files from or to your computer use the following commands:

pscp myfile.txt username@hpc.uct.ac.za:/home/username
pscp username@hpc.uct.ac.za:/home/username/myfile.txt .
Note the ‘.’ at the end of the last example.

Alternately you can download a graphical interface such as WinSCP. You would login to the cluster in much the same fashion as above, except you will be presented with a dual pane graphical interface similar to Windows Explorer where you can drag and drop files between hpc and your computer.

winscp

 

I have a Mac:
-------------

Logging in and transferring files

Most Apple MAC OS’s come with ssh and scp preinstalled. From Applications, Utilities select Terminal.

Apple

Then type:

ssh username@hpc.uct.ac.za
to login and

scp myfile.txt username@hpc.uct.ac.za:/home/username
scp username@hpc.uct.ac.za:/home/username/myfile.txt .
to transfer files.

I have a Linux box:
-------------------

Logging in and transferring files 

Most Linux distros come with ssh and scp preinstalled. If you are using the command line you would type:

ssh username@hpc.uct.ac.za
to login and

scp myfile.txt username@hpc.uct.ac.za:/home/username
scp username@hpc.uct.ac.za:/home/username/myfile.txt .
to transfer files from and to your computer.

Alternately we also recommend rsync, although if you’re transferring files to the cluster this application would need to be installed on the source host.  Rsync is preferred as it will do a sync of data not yet copied in the case of a copy being interrupted.

To copy a folder from your linux box to hpc use:

rsync -avr FolderName username@hpc.uct.ac.za:/scratch/username/

This will copy FolderName to your scratch folder. NB do not put a trailing slash on FolderName, otherwise the contents of FolderName will be copied to scratch which is not generally what one wants.

 

If you are using a graphical interface you can launch the command line from the menu. In most distros it is called the Terminal, in the example below, Ubuntu, it is found under Applications, Accessories.

terminal

 

Off-Campus logins
-----------------

If you need to access cluster from outside of UCT you will need to do so by making use of the VPN.

