### Getting the MicroBit to work on Windows


Prerequisites:
- Windows 11
- Minimum WSL version of `5.10.60.1`


We will using `usbipd` 

#### Installation:
- `winget install --interactive --exact dorssel.usbipd-win`

On the WSL side we will run
- `sudo apt install linux-tools-generic hwdata`

  `sudo update-alternatives --install /usr/local/bin/usbip usbip /usr/lib/linux-tools/*-generic/usbip 20`

#### Working with the MicroBit

First, list devices using `usbip --list` It should look something like this:
![Displaying USBIP in Windows CMD](./usbipd-display.png)


See which `busid` your microbit is connected to

Using that, now run `usbipd wsl attach --busid <busid>`

For reference, this is the command I ran: `usbipd wsl attach --busid 1-7`

Now go over to your WSL client and run `lsusb`, if your MicroBit is showing up, you did everything correctly!



#### Errors:

If you are running into any errors, first ensure that your wsl client is upto date. 

If the issue continues, ensure that there are no processes using the MicroBit.

If issues continue, restart PC and try again.





#### Microsoft guide
You can also follow [this](https://learn.microsoft.com/en-us/windows/wsl/connect-usb) guide for more information if this
approach did not work for you.