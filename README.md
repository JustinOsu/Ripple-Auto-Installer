<h1 align="center">
  <a href=https://ripple.moe>Ripple</a> Auto Installer
</h1>
<h4 align="center"><a href=https://ripple.moe>Ripple</a> Stack Installation Helper</h4>

<p align="center">
  <img src="https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/X/ripple.svg"/>
</p>

## Attention
<b>**THIS SCRIPT IS NOT FOR LOCAL PC (localhost) AND IT IS FOR ADVANCED USERS!**</b><br>
This script gives you a base and foundation if you're willing to install your own Ripple instance. You should try to figure out most of the things by yourself. If you fail or unable to do then you're not qualified enough but keep trying hopefully you'll evolve one day.
* ORIGIN: https://github.com/Uniminin/Ripple-Auto-Installer
* MIRROR: https://zxq.co/Uniminin/Ripple-Auto-Installer

<b>**If You Want A Bit less painful and Easier Version Then visit:**</b><br>
* Hazuki's RAI: ~~https://github.com/osuthailand/ripple-auto-installer~~ Removed/Private
* You Might want to look at Ripple's Wiki: https://github.com/osuripple/ripple/wiki/How-to-setup-ripple

### Requirements
* A Linux VPS. Debian Based Distros are recommended.<br>
Note: Ubuntu 16.04/18.04 is atleast recommended if you want to directly start without any additional tweaking!<br>

### Features
* A configurable shell script for installing Ripple Stack
* Everything is Pre-ready 
* Simple and user friendly Installation
* Installs most of the things for your server within minutes

### Running the Script (Instructions)
```bash
$ wget https://raw.githubusercontent.com/Light-Ripple/Ripple-Auto-Installer/master/Main/ripple.sh
$ chmod +x ripple.sh 
$ sudo ./ripple.sh --help
```
Note: use sudo. for example: `sudo ripple.sh --all` to install & setup full ripple stack with dependencies.

### After Installation Steps
* Certificate  
Edit <a href=https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/Main/openssl.cnf>openssl.cnf</a> and run <a href=https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/Main/gencert.sh>gencert.sh</a> to generate certificates. Use `cert.pem` and `key.pem` in your nginx configuration and `cert.pem` in your switcher.  
Use this on your site:
```
git clone https://github.com/Neilpang/acme.sh.git
cd acme.sh
./acme.sh --issue --standalone -d osu.ripple.moe -d c.ripple.moe -d a.ripple.moe -d oldripple.ripple.moe
```  
* Proxy  
Edit and include <a href=https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/Main/ripple.conf>ripple.conf</a> in your nginx.conf

### Edit Config
Edit all configs.
* /RIPPLE/pep.py and run/edit `nano config.ini`
* /RIPPLE/lets and run/edit `nano config.ini`
* /RIPPLE/hanayo and run/edit `nano hanayo.conf`
* /RIPPLE/rippleapi and run/edit `nano api.conf`
* /RIPPLE/old-frontend and run/edit `nano inc/config.php`

### Start Server
You might want to look at this tmux cheatsheet first: <a href=https://tmuxcheatsheet.com/v>Click ME!</a> |
Create tmux sessions:`tmux new -s tmux_session_name` and go to:
* /RIPPLE/pep.py and run `python3.6 pep.py`
* /RIPPLE/lets and run `python3.6 lets.py`
* /RIPPLE/OSU-AVATAR-SERVER and run `python3.6 avatar-server.py`
* /RIPPLE/hanayo and run `./hanayo`
* /RIPPLE/rippleapi and run `./rippleapi`

### Domain
Make sure you set your DNS like this:
```
* YOUR-DOMAIN
* c.YOUR-DOMAIN
* i.YOUR-DOMAIN
* a.YOUR-DOMAIN
* s.YOUR-DOMAIN
* old.YOUR-DOMAIN
```

<p align="center">
  <img src="https://i.imgur.com/0ksWZR9.png"/>
</p>

### OSU!API
* You can get OSU!API Key Here:<a href=https://old.ppy.sh/p/api>OSU!API</a>


### Tested OS

| NO | Status| Platform|
|----|-------|---------|
|1|[![](https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/X/fail.svg)](https://github.com/uniminin)| Bedrock
|2|[![](https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/X/pass.svg)](https://github.com/uniminin)| Ubuntu 19.10
|3|[![](https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/X/pass.svg)](https://github.com/uniminin)| Debian
|4|[![](https://github.com/light-ripple/Ripple-Auto-Installer/blob/master/X/pass.svg)](https://github.com/uniminin)| Centos

### Contact
You can ~~add me on Discord or~~ join my discord server and ask for help but don't expect us to create a server for youself.
 My Discord:~~`uniminin#5959`~~ you may contact with me on the server.
* Discord Server: <a href=https://discord.gg/qyD3sPe>Developer I/O</a>

### Credits
Thanks to <a href=https://github.com/semyon422>semyon422</a> for your <a href=https://github.com/semyon422/open-ripple>open-ripple</a> guide.

### License :scroll: [![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
This project is licenced under the GNU Affero General Public License V3. For more information, see the file `LICENSE` or visit https://www.gnu.org/licenses/agpl-3.0.
