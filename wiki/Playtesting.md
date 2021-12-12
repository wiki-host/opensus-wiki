OpenSuspect is currently pre-alpha, and thus does not have binaries ready to download and play. However, the project can still be tested and played by cloning the repo, and opening the project in Godot. This is a tutorial to get the game up and running on your own machine.

The [troubleshooting](https://matrix.to/#/#opensus_troubleshoot:matrix.org) and [playtesting](https://matrix.to/#/#open_sus_playing:matrix.org) rooms on matrix may be of use to you if you get stuck, make sure to check them out.

## Step 1: Install Godot
Godot is the game engine used by the OpenSuspect project. It is required to edit and test the game.
### How to get Godot
For Ubuntu based distros: `sudo apt install godot3`<br/>
AUR package for Arch based distros: https://aur.archlinux.org/packages/godot/<br/>
Godot binary from website (for other distros): https://godotengine.org/download/linux<br/>

## Step 2: Make sure git is installed
Some distributions come with git pre-installed. Others will need it to be installed. Try using your package manager to install it, to make sure it is installed.
For Ubuntu based distros: `sudo apt install git`
For Arch based distros: `sudo pacman -S git`

## Step 3: Install git-lfs
Git-lfs stores large assets for the OpenSuspect project, so as not to consume too much space in the git repo. This makes it a requirement for play-testing the game, else art assets wouldn't show up in game.
### How to get git-lfs
For Ubuntu based distros: `sudo apt install git-lfs`<br/>
For Arch based distros: `sudo pacman -S git-lfs`<br/>
Git-lfs binary from website (for other distros): https://git-lfs.github.com/

## Step 4: Setup git-lfs
Git-lfs has a little bit of setup required in order for it to work. Check out this guide [here](https://github.com/opensuspect/opensuspect/wiki/Contributors#howto-install-git-lfs) in order to get it working.

## Step 5: Clone the repo
This part is easy. Make sure to clone the repo into the previously setup folder.<br/>
`git clone https://github.com/opensuspect/opensuspect.git opensusdir`

## Step 6: Load in Godot
Start Godot using the terminal by running `godot`, or navigating to the application in your menu. Once loaded, navigate to "Import" and then use the file picker to load "opensusdir/src/project.godot".