<h1 align="center">Welcome to sd2cP :mage: </h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-2.0-blue.svg?cacheSeconds=2592000" />
  <img src="https://img.shields.io/badge/bash-%3E%3D3.00.20-blue.svg" />
  <a href="https://github.com/jumpline/sd2cp#readme" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="https://github.com/jumpline/sd2cp/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" />
  </a>
  <a href="https://github.com/jumpline/sd2cp/blob/master/LICENSE" target="_blank">
    <img alt="License: GNU" src="https://img.shields.io/github/license/jumpline/sd2cp" />
  </a>
</p>

> VDS to cPanel Migration Script

### :house_with_garden: [Homepage](https://github.com/jumpline/sd2cp)

<!-- TOC START min:1 max:3 link:true asterisk:true update:true -->
  * [Prerequisites](#prerequisites)
  * [Author](#author)
  * [About sd2cp](#about-sd2cp)
  * [:handshake: Contributing](#handshake-contributing)
  * [:star: Show your support](#show-your-support)
  * [:pencil:	 License](#pencil-license)
<!-- TOC END -->



## Prerequisites

- bash >=3.00.15

## Author

:bust_in_silhouette: **Jumpline**

* GitHub: [@jumpline](https://github.com/jumpline)

***

## About sd2cp

:information_source: sd2cp is a migration application written to automate migrations between the legacy product "Sphera VDS Control Panel" to the new and ever updated cPanel control panel.

I have re-written the main master scripts and compressed them into one script. Now you no longer have to run 4 scripts. You now run 1 script, and this script will do all the work.

This sd2cp.sh script can be ran on the VDS Master for packaging the account. The same script can also run on the cPanel server.
<br /><br /><br />

## Usage

This is very basic. 1 script does all the work.


1. Login to the VDS server (not as a client, but as root), download this file and extract it:
```
    
scp -P1022 $YOUR_SSH_USE@ansible01.myhostcenter.com:/opt/Migration_Scripts/sd2cp-release.tar.gz /root/
cd /root
tar zxvf sd2cp-release.tar.gz
cd sd2cp-release/
chmod 755 *.sh

```
2. To Package the account(s) run the following command. It will take 1 or more usernames:
```
    ./sd2cp.sh user1 user2 user3
```
3. Rsync or scp the /root/sd2cp_restore_USERNAME.tar file, to the cPanel destination server.

4. Login to the cPanel server, and repeat steps 1, and 2. Then step repeate step 3, of running the script with the same usernames. It will search /root/ for the .tar file with the corresponding usernames, and restore them.
```
    
scp -P1022 $YOUR_SSH_USER@ansible01.myhostcenter.com:/opt/Migration_Scripts/sd2cp-release.tar.gz /root/
cd /root
tar zxvf sd2cp-release.tar.gz
cd sd2cp-release/
chmod 755 *.sh
./sd2cp.sh user1 user2 user3

```
5. At the end of the script, you will see it output the main password used for everything on the account, you'll want to take note of these, lest you want to manually reset every password on the account. It'll be "username password" format
```

COPY THESE PASSWORDS NOW!!! THEY EXIST NOWHERE ELSE. 
IF YOU DONT SAVE THESE NOW, YOU WILL HAVE TO REGENERATE FOR ALL CUSTOMERS MIGRATED 
These corresponding password is used with anything that has a password in cPanel. 

USERNAME MkjK2mz0NjM4

```
Logs for everything this script has done are in /var/log/sd2cp_logs/
<br /><br /><br />



***
## :handshake: Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/jumpline/sd2cp/issues).

## :star: Show your support

Give a ⭐️ if this project helped you!

## :pencil:	 License

Created by [Stephen Chaffins](https://github.com/jumpline).<br />
<!-- This project is [MIT](https://github.com/jumpline/sd2cp/blob/master/LICENSE) licensed. -->
