Arch Linux
==========

Navigator
---------
[Installing JDK (Java Development Kit)](#installing-jdk-java-development-kit)

[Install other necessary tools](#install-other-necessary-tools)

[Download Repo and set PATH](#download-repo-and-set-path)


Installing JDK (Java Development Kit)
-------------------------------------
P.S. Since AOSP 9, OpenJDK is bundled into the repo, not depended on what you have installed. You can skip to [Install other necessary tools](#install-other-necessary-tools)

After you have deleted all the JDK versions on your computer, it's time to install new ones, different Android versions requires different JDK, please follow the list below:
Android version|JDK Version
---------------|-----------
Android 1.5 - 2.2|OpenJDK 5
Android 2.3.x - 4.4.x|OpenJDK 6
Android 5.x - 6.x |OpenJDK 7
Android 7.x - 8.x|OpenJDK 8

To install, run this command in the terminal:

`sudo pacman -S jdk*-openjdk`

Replace * with the version you want to install.

You also have to set JAVA_HOME, run the following command:

`export JAVA_HOME=/usr/lib/jvm/java-*-openjdk`

Replace * with the version you have installed.

Install other necessary tools
-----------------------------
To be able to build AOSP, you need to install a set of software packages and libraries which give you the tools to compile source code into binary files that can run on your device.

Run this command in the terminal:

`sudo pacman -S lib32-gcc-libs git gnupg flex bison gperf sdl wxgtk2 squashfs-tools curl ncurses zlib schedtool perl-switch zip unzip libxslt python2-virtualenv bc rsync ncurses5-compat-libs lib32-zlib lib32-ncurses lib32-readline lib32-ncurses5-compat-libs`

If you want to build AOSP 10, you have to run this command:

`sudo pacman -S base-devel multilib-devel gcc repo git gnupg gperf sdl wxgtk2 squashfs-tools curl ncurses zlib schedtool perl-switch zip unzip libxslt bc rsync ccache lib32-zlib lib32-ncurses lib32-readline ncurses5-compat-libs lib32-ncurses5-compat-libs`

Download Repo and set PATH
--------------------------
In order to access and download the source code you want to compile, you need to install the Repo tool that is provided by Google.

Run the following command to install the repo tool:

`sudo pacman -S repo`

The Android build process expects python to be python2. Prepend it to the PATH: 

`mkdir bin`

`ln -s /bin/python2 bin/python`

`export PATH=$PWD/bin:$PATH`
