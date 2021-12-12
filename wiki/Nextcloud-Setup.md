All of OpenSuspect's art assets and game design notes are stored on our shared NextCloud server. As you get more involved in OpenSuspect, it is expected that you will join the Nextcloud server. This is a guide for setting up your Nextcloud account, joining the correct circles, and setting up filesync.

### Setting up an Account
Setting up an account for OpenSuspect's Nextcloud is easy. Go to https://nextcloud.opensuspect.com/apps/registration/ and input your email address. You will then receive an email with further instructions.

Once you have set up the account, login to the Nextcloud, and then navigate to the circles tab.
![Circles Tab](https://nextcloud.opensuspect.com/apps/files_sharing/publicpreview/irF2XezY77rwkGL?x=1920&y=468&a=true&file=circles-nav.png)

Now you can join the relevant circles you wish to access. Select the team circle from the list (you may need to press "All Circles", and refresh for it to load).
![Team List](https://nextcloud.opensuspect.com/apps/files_sharing/publicpreview/5zZpAWWf8YPGYjq?x=1920&y=468&a=true&file=circles-team.png)

Then press the join button, above the selected team's member list. <br/>
![Join](https://nextcloud.opensuspect.com/apps/files_sharing/publicpreview/aXHZkxjaNBJgeAC?x=1920&y=468&a=true&file=circles-join.png&scalingup=0)

This will then send a join request to the circle leaders. The next step is to notify Moxvallix or NiceMicro on Element, and they will allow you into the circles.

### Setting up File Sync
Setting up the Nextcloud file sync is a good idea if you find yourself using files frequently on Nextcloud. The file sync allows you to keep a local copy of files shared with you in your filesystem, and access and modify the files the same way you would normally.

The sync client can be installed following instructions here: https://nextcloud.com/install/#install-clients.
After installation, you will need to login. Open the sync program, and add a new account. Select "Login to your Nextcloud", then put in the OpenSuspect Nextcloud URL. (https://nextcloud.opensuspect.com)
![Sync URL](https://nextcloud.opensuspect.com/apps/files_sharing/publicpreview/8xF7GjCz75qLmca?x=1920&y=468&a=true&file=sync-url2.png)

After pressing "Next", your browser should open, and automatically log you in, if you are already signed in in your browser. Then it will take you to the folder sync setup. It is advised that you create a folder called "OpenSuspect" either in your home directory, or in a projects folder. Select this folder for the file sync, as shown in below image.
![Files](https://nextcloud.opensuspect.com/apps/files_sharing/publicpreview/gREJLpeXFRyGgrt?x=1920&y=468&a=true&file=sync-folders.png&scalingup=0)

After configuring the folders to your liking, press connect, and you are done.

### Other useful things to set up
Nextcloud provides file manager integrations for its sync client. Check your distro's repos for such packages (just type nextcloud nautilus etc. in search). These allow for handy status symbols on shared folders.

Also make sure that Nextcloud sync is set to autostart on login. Check your autostart configuration, and add it if it isn't setup.