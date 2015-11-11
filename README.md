resin-ssh
=========

This is a node.js port of the [resin-ssh-python](https://github.com/resin-io-projects/resin-ssh-python). It's essentially a resin container that runs dropbear on boot which allows for ssh access. 

NOTE: This container enables SSH access as root with a PASSWORD stored in plain text - Do not use in production without modifications.

#### SSH into you're device. 

Add an environment variable called PASSWD with the value to set as root password.

![alt text](https://github.com/craig-mulligan/resin-ssh-node/blob/master/img/envar.png "creating envar")

Get your device's IP address from the resin dashboard. Then run

```sh
$ ssh root@<YOUR-DEVICE'S-IP>
```

The code you just pushed is kept in the app directory.

```sh
$ cd /usr/src/app
```


At after pushing you may encounter and re-sshing back into the device you may encounter this error message as the host key changes when an update occurs on the device.


```sh
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
```

To get around this remove the key.

```sh
$ ssh-keygen -R <YOUR-DEVICE'S-IP>
```

It will then work as expected

```sh
$ ssh root@<YOUR-DEVICE'S-IP>
```
