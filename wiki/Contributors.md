# Contributing to OpenSuspect
OpenSuspect's Development is organised across three different services; Github for hosting and issues, Nextcloud for document collaboration / sharing, and Matrix for general discussion and coordination. This is a guide that will take you through the steps needed to use these services, and start contributing.

## Step 1: Join Matrix Rooms
OpenSuspect uses a set of chat rooms in Matrix, each with a particular purpose. There are 5 rooms dedicated to the contribution teams; Programming, Art, Game Design, Branding and Translation. Depending on the areas you are interested to contribute to, join the correlating chat rooms. If you are feeling brave, join them all!

As well, there are some general rooms that are useful for all contributors to join. General is the room for general discussion about the project, Leaders Room is where the leaders make some key decisions. Announcements is where important announcements for the project are made.

Matrix rooms can be accessed using a matrix client, such as Element. [Link to Element](https://element.io/)

Links to the Contribution Teams:
[Art](https://matrix.to/#/#open_sus_art:matrix.org), [Programming](https://matrix.to/#/#open_sus_programming:matrix.org), [Game Design](https://matrix.to/#/#open_sus_gameplay:matrix.org), [Branding](https://matrix.to/#/#open_sus_brand:matrix.org), [Translation](https://matrix.to/#/#open_sus_translate:matrix.org).

Links to the Project Rooms:
[OpenSuspect General Discussion](https://matrix.to/#/#opensuspect:matrix.org), [Leaders](https://matrix.to/#/#open_sus_lead:matrix.org), [Announcements](https://matrix.to/#/#open_sus_announce:matrix.org), [Troubleshooting](https://matrix.to/#/#opensus_troubleshoot:matrix.org
), [Suggestions](https://matrix.to/#/#open_sus-suggestions:matrix.org), [Random](https://matrix.to/#/#open_sus_rand:matrix.org), [Memes](https://matrix.to/#/#memes_opensus:matrix.org).

## Step 2: Clone the Project
OpenSuspect uses git to manage the project's code and assets. As well, git-lfs is needed for large file management. Follow the git-lfs howto below, to prepare a folder ready to clone down the project.

### Howto: Install git-lfs

> To handle large files better, we use git-lfs. First, install the package, such as 
> `sudo pacman -S git-lfs` on Arch Linux. 
> `sudo apt install git-lfs` on Debian/Ubuntu

> Then create an empty new Git repository(if you haven't all ready):
> `mkdir opensusdir`

> Change to that directory
> `cd opensusdir `

> And do an init
> `git init `

> Navigate to your Git repository (where the .git directory is located) and execute the following command in order to activate Git LFS:
> `git lfs install`

After this, the project can be cloned down into the prepared folder. `git clone https://github.com/opensuspect/opensuspect.git`

## Step 3: Set up Godot
OpenSuspect uses the Godot game engine. If you would like to contribute code, or test the latest state of the game, you will need to install the latest version of Godot. OpenSuspect is written in GDscript, Godot's native scripting language. The game can be opened for editing in Godot, by navigating to src/ and opening project.godot in Godot.

If you get an error when loading the project about missing resources, you have not installed git-lfs correctly.

## Step 4: Contribute!
You should now have the basic requirements to start contributing to OpenSuspect. Make sure to discuss with other contributors about more team-specific requirements, such as [Nextcloud](https://nextcloud.opensuspect.com), or any other needed software / files. If you are planning to make a pull request, be sure to hit up someone in the General or Programming chat, for guidance on submissions. Also be sure to check out our [[git instructions]] page, in order to understand our few rules we have in place that keep our project neat and organised.