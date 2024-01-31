# Liverpool Uni Linux Farm tutorial for VSCode
How to connect to the Linux farms over SSH in VSCode. Useful in COMP284.
VSCode is a waaaaaaayyy better text editor than the recommended gedit, and it also helps you keep all your stuff in one place rather than using several different IDEs / editors.

**Note:** For Mac users use `Cmd` instead of `Ctrl` in shortcuts.

# Step 1
Open VSCode and under _Extensions_ `(Ctrl-Shift-X)`, search for "ssh" and install "Remote - SSH" and "Remote - SSH Editing...".

![VSCode extensions](https://i.imgur.com/6Zhw0kL.jpg)

# Step 2

Open the VSCode settings search by pressing `Ctrl-Shift-P` and type "open ssh". The top option should read "Remote-SSH: Open SSH Configuration File". Press `Enter`.

You should now be presented with a couple options, hit `Enter` on the one that looks like _<your_user_area>\.ssh\config_.

![dialogue options](https://imgur.com/XKnJOBy.jpg)

# Step 3

Now we need to enter our connection settings in the format:

    Host <host>
        HostName <hostname>
        MACs <MAC>
        User <username>

**Note:** the MAC is an encryption algorithm used when logging in. Lots of them will work but I found that a SHA512 one works fine, so I'll be using that.

1. Replace `<hostname>` and `<host>` with the address of a UoL Linux server, such as `lxfarm01.csc.liv.ac.uk` (you can choose from 01 up to 08 I think, I'm not really sure it matters either).

2. Replace `<MAC>` with `hmac-sha2-512` (this is the SHA512 algorithm from the note above)

3. Replace `<username>` with your university username (do not include the @liverpool.ac.uk part)

In my case, my config file looks like this:

![my config file](https://imgur.com/5bFXNkZ.jpg)

Save the file.

# Step 4

Once we've made the config file, we should be able to connect.

Click the _Remote Explorer_ in the left side of VSCode (blue arrow), then click _Refresh_ (red arrow).

![remote access panel](https://imgur.com/nwp1nHn.jpg)

Your connection should now show up. Right-click and choose current or new window to start the connection process, where you will be prompted for your password.

**Note:** sometimes VSCode will not be able to figure out what system it is connecting to, and it will show a few options. Just click Linux.

# Step 5

Once connected, we will have access to all our files on the Linux systems. In the left-hand side of the screen click _Explorer_ `(Ctrl-Shift-E)` and open a folder. It will default to your home directory on the server. Click "OK" in the prompt.

All done! Now you can access your files in the _Explorer_ panel, edit them, create them and so on... If you'd like to access the terminal press `Ctrl-Shift-'` or click _Terminal_ > _New Terminal_ in the toolbar.


Thanks for reading this guide and I hope it helped. If you have any questions or something isn't working please create an issue on GitHub and I'll do my best to help.







