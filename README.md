resin-ssh
=========

This is a node.js port of the resin-ssh for python projects.

NOTE: This container enables SSH access as root with a PASSWORD stored in plain text - Do not use in production without modifications.

Resin container that runs dropbear on boot.

Add an environment variable called PASSWD with the value to set as root password.

[logo]: 


At after pushing you may encounter and re-sshing back into the device you may encounter this error message as the host key changes when an update occurs on the device.

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.

To get around this remove the key.

```sh
$ ssh-keygen -R <YOUR-PI'S-IP>
```

And then it will work as expected. 

```sh
$ @root<YOUR-PI'S-IP>
```