**`Last updated`** : `September 2025`

---

![logo](./previews/logo.png) <br />

Termux Desktop is based on some **dotfiles** & **scripts**, which will help you to setup a graphical environment in **Termux**. Follow the steps if you'd like to install a nice graphical environment on your device <br />

|Openbox WM|Another Style|
|--|--|
|![desktop](./previews/main_1.png)|![desktop](./previews/main_2.png)|

### What is Termux?

Termux is an *Android Terminal emulator* and a **Linux environment** app that works directly with **no root** access or setup required. A minimal base system is installed automatically - additional packages are available using the *PKG/APT package manager*. More [Here](https://termux.com/)... <br />

### How do I install Termux?

You can download Termux from the Google Play Store, or you can get it from F-Droid. <br />

- Get it on [Github](https://github.com/termux/termux-app)
- Download from [F-Droid](https://f-droid.org/packages/com.termux/) <br />

More information about installation is [here](https://wiki.termux.com/wiki/Main_Page) <br />

### Preparation

Install `Termux` & `Termux:API` on your phone. It's recommended to install *Termux API* application as many desktop elements are dependent on it.

> This setup is created and tested on :
>
> Device - **Samsung Galaxy A3 2016** <br />
> Android - **Android 10 (Q)** (LineageOS 17.1) <br />
> CPU Type - **armv8l**

### Installation

After installing both applications above, open `Termux` and follow the steps below -

- Update Termux packages and install `git`. This is required!
```
pkg upgrade && pkg install git
```

- Clone this repository
```
git clone --depth=1 https://github.com/NotNoelChannel/termux-desktop.git
```

> **Warning** : We assume that you do this on a fresh Termux install. The `setup.sh` script makes a backup of every file it replaces but it's still recommended that you manually backup your files in order to avoid conflicts. <br />

- Change to cloned directory and run `setup.sh` with *--install* option
```
cd termux-desktop
chmod +x setup.sh
./setup.sh --install
```

> If script `setup.sh` fails during package installation (due to network issues or if a package isn't found; edit the setup.sh manually), you can re-execute it again.

- During installation, you'll be asked to set up password for **VNC** -
```
[*] Setting up VNC Server...

You will require a password to access your desktops.

Password:
Verify:
Would you like to enter a view-only password (y/n)? n
```

> Note that passwords are not visible when you are typing them and minimum password length is 6 characters.
> Remember the password you typed as it'll be required to connect via VNC Client.
- If everything went alright, then you will see this message -
```
New 'localhost:1 ()' desktop is localhost:1

Creating default startup script /data/data/com.termux/files/home/.vnc/xstartup
Creating default config /data/data/com.termux/files/home/.vnc/config
Starting applications specified in /data/data/com.termux/files/home/.vnc/xstartup
Log file is /data/data/com.termux/files/home/.vnc/localhost:1.log

[*] Server Is Running...

TigerVNC server sessions:

X DISPLAY #     PROCESS ID
:1              XXXXX
```
> It means that X (VNC) server is available on display 'localhost:1'. <br />

That's it. `Termux Desktop` is installed successfully. After you are done, *restart Termux* and enter `startdesktop` command to start *vncserver* and connect via VNC Client. <br />
```
startdesktop

[*] Starting VNC Server...

New 'localhost:1 ()' desktop is localhost:1

Starting applications specified in /data/data/com.termux/files/home/.vnc/xstartup
Log file is /data/data/com.termux/files/home/.vnc/localhost:1.log
```

### Uninstall

If you'd like to uninstall Termux Desktop, just run `setup.sh` with *--uninstall* option. Just keep the `setup.sh` script and delete the cloned repository to save space. The command below will remove all the packages and delete all the config files it installed, **including the changes you've made**.
```
./setup.sh --uninstall
```

***VNC Client***

Now you need a VNC client app to connect to server. If you are on Android, it's recommended to use this client: [VNC Viewer](https://play.google.com/store/apps/details?id=com.realvnc.viewer.android). You can use [TigerVNC](https://tigervnc.org/) if you're trying to connect to server by a computer (Windows or Linux).

Determine port number on which VNC server listens. It can be calculated like this: 5900 + {display number}. So for display 'localhost:1' the port will be 5901. <br />

Now open the VNC Viewer application and create a new connection with the following information (assuming that port is 5901) - <br />
```
Address:
127.0.0.1:5901

Name:
Termux
```
Now launch it. You will be prompted for `password` that you entered during installation. After entering password, you'll be headed directly to this desktop - <br />

![desktop](./previews/desk_1.png) <br />

### First Impression

Let's take a look at following installed programs you'll get here - 

|File Manager|Text Editor/IDE|
|--|--|
|![img](./previews/desk_2.png)|![img](./previews/desk_3.png)|

|Terminal Emulator|
|--|
|![img](./previews/desk_4.png)|

|Openbox Menu|Many CLI based Programs|
|--|--|
|![img](./previews/desk_6.png)|![img](./previews/desk_7.png)|

|vim & htop|ranger & calcurse|mutt & elinks|mpd & ncmpcpp|
|--|--|--|--|
|![img](./previews/desk_8.png)|![img](./previews/desk_9.png)|![img](./previews/desk_10.png)|![img](./previews/desk_11.png)|

Rofi Application launcher and Applets - 

|App Launcher|Music Player|
|--|--|
|![img](./previews/rofi_1.png)|![img](./previews/rofi_2.png)|

|Battery Status|Exit Menu|Network Info|
|--|--|--|
|![img](./previews/rofi_3.png)|![img](./previews/rofi_5.png)|![img](./previews/rofi_4.png)|

### Styles

There are total *Eight different styles/themes* available in this setup. To change style, `Right click on desktop > Preferences > Change Style` and select the one you want to apply.

|Default|Beach|Forest|Grid|
|--|--|--|--|
|![img](./previews/style_1.png)|![img](./previews/style_2.png)|![img](./previews/style_3.png)|![img](./previews/style_4.png)|

|Manhattan|Slime|Spark|Wave|
|--|--|--|--|
|![img](./previews/style_5.png)|![img](./previews/style_6.png)|![img](./previews/style_7.png)|![img](./previews/style_8.png)|

### Applications of `Termux Desktop`

Well, These are some ideas or things you can do with termux desktop. From Learning coding to Penetration testing, Chatting over IRC to Browsing web and Downloading file, Playing classic retro games to run Windows from 90s. 

- Learn and practice you coding skill without having a laptop

|Python|Bash|
|--|--|
|![img](./previews/app_1.png)|![img](./previews/app_2.png)|

- Chatting, Web Browsing and Downloading files

|Hexchat & Pidgin|Browsing Wiki|
|--|--|
|![img](./previews/app_3.png)|![img](./previews/app_5.png)|

- Penetration Testing and learning cybersecurity

> I'm not doing anything **illegal** or sponsoring any kind of **hacking and cracking**. *Termux is a powerful tool, use it with responsibilities.* <br />

|Metasploit - Sherlock - Socialfish - Zphisher - Sqlmap|
|--|
|![img](./previews/app_6.png)|

- Play classic retro games or run Microsoft Windows from 90s with `Dosbox`

|Turbo C++, Windows 1 and Windows 3|Duke and Blue Brothers|
|--|--|
|![img](./previews/app_7.png)|![img](./previews/app_8.png)|

|Mario and Pacman|Prince of Persia (both)|
|--|--|
|![img](./previews/app_9.png)|![img](./previews/app_10.png)|

|Wolfenstein and Turrican2|SuperKarts and Spiderman|
|--|--|
|![img](./previews/app_11.png)|![img](./previews/app_12.png)|

You'll probably get the idea of possible things you can do with Termux and how Termux Desktop makes it more easy. 

### Keybindings

Here's some shortcut keys you want to use to speed up your work. For more, `Right click on Desktop > Keybinds`

|Keys|Action| ----- |Keys|Action|
|--|--|--|--|--|
| `W-1` | Go To Desktop 1 |  |`S-W-1` | Send To Desktop 1 |
| `W-2` |	Go To Desktop 2 |  |`S-W-2` | Send To Desktop 2 |
| `W-3` |	Go To Desktop 3 |  |`S-W-3` | Send To Desktop 3 |
| `W-4` |	Go To Desktop 4 |  |`S-W-4` | Send To Desktop 4 |
| `W-5` | Go To Desktop 5 |  |`S-W-5` | Send To Desktop 5 |
||||||
| `W-S-Left` | Send To Prev Desktop |  | `W-S-Right` | Send To Next Desktop |
| `A-Tab` | Next Window (Current Workspace) |  |`W-Tab` | Next Window (All Workspaces) |
||||||
| `W-h` | Move to TopLeft |  | `W-j` | Move to BottomLeft |
| `W-k` | Move to TopRight |  | `W-l` | Move to BottomRight |
| `W-Left` | Move To Left Edge |  | `W-Right` | Move To Right Edge |
| `W-Up` | Maximized |  | `W-Down` | Unmaximized |
||||||
| `W-q/c` | Close Windows |  | `A-r/m` | Toggle Resize/Move |
| `W-Space` | Openbox Menu |  | `W-p/A-F1` | App Launcher |
| `W-d` | Toggle Desktop |  | `W-v` | Set Tasks |
||||||
| `W-f` | File Manager |  | `W-e` | Text Editor |
| `W-t/return` | Terminal |  | `W-w` | Web Browser |
| `W-x` | Exit Menu |  | `W-m` | Music Menu |
| `W-b` | Battery Menu |  | `W-n` | Network Menu |
| `C-A-v` | Vim |  | `C-A-r` | Ranger |
| `C-A-h` | Htop |  | `C-A-n` | Nano |

### Additional Tools

You can install additional tools for termux, to make it visually look good.
1. [Oh my zsh](https://github.com/adi1090x/termux-omz), set up zsh with [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) framework. (Already Added in this setup)
2. [Termux style](https://github.com/adi1090x/termux-style), Change color and fonts in termux.

### FYI

- If you face any problem or get any error, you can create an issue & I'll try to help.
- Edit `~/.local/bin/email` and put your Email ID and Password (Use an App password) to show unread mails on polybar.
- You may need to edit some config files accoring to your need (`~/.mutt/muttrc`, `~/.gitconfig`)
- Have Fun, Share this repository with your friends.

