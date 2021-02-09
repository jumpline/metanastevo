<h1 align="center">Welcome to Metanastevo (VDS2CP) :mage: </h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.5-blue.svg?cacheSeconds=2592000" />
  <img src="https://img.shields.io/badge/bash-%3E%3D3.00.15-blue.svg" />
  <a href="https://github.com/jumpline/metanastevo#readme" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="https://github.com/jumpline/metanastevo/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" />
  </a>
  <a href="https://github.com/jumpline/metanastevo/blob/master/LICENSE" target="_blank">
    <img alt="License: GNU" src="https://img.shields.io/github/license/jumpline/metanastevo" />
  </a>
</p>

> VDS to cPanel Migration Script

### :house_with_garden: [Homepage](https://github.com/jumpline/metanastevo)

<!-- TOC START min:1 max:3 link:true asterisk:true update:true -->
  * [Prerequisites](#prerequisites)
  * [Author](#author)
  * [About Metanastevo](#about-metanastevo)
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

## About Metanastevo

:information_source: metanastevo is a migration application written to automate migrations between the legacy product "Sphera VDS Control Panel" to the new and ever updated cPanel control panel.

I have re-written the main master scripts and compressed them into one script. Now you no longer have to run 4 scripts. You now run 1 script, and this script will do all the work.

This metanastevo.sh script can be ran on the VDS Master for packaging the account. The same script can also run on the cPanel server.
<br /><br /><br />

## Usage

This is very basic. 1 script does all the work.
1. Login to the VDS Master server (not as a client), download this file:
```
    wget --no-check-certificate https://raw.githubusercontent.com/jumpline/metanastevo/main/metanastevo.sh; chmod 755 metanastevo.sh
```
2. To Package the account run the following command. It will take 1 or more usernames:
```
    ./metanastevo.sh user1 user2 user3
```
3. Rsync or scp the /root/metanastevo_restore_USERNAME.tar file, to the cPanel destination server.

4. Login to the cPanel server, and repeat steps 1 and 2.
```
    wget --no-check-certificate https://raw.githubusercontent.com/jumpline/metanastevo/main/metanastevo.sh; chmod 755 metanastevo.sh
    ./metanastevo.sh user1 user2 user3
```

Logs for everything this script has done is at /var/log/metanastevo.log
<br /><br /><br />


***
## :handshake: Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/jumpline/metanastevo/issues).

## :star: Show your support

Give a ⭐️ if this project helped you!

## :pencil:	 License

Created by [Stephen Chaffins](https://github.com/jumpline).<br />
#This project is [MIT](https://github.com/jumpline/metanastevo/blob/master/LICENSE) licensed.
