# WHMCS Vagrant
A vagrant/puppet configuration to easily provision a local development environment for use with WHMCS.

Forked from https://github.com/nem-c/whmcs6-vagrant-puppet

Based on CentOS 6.5<br/>
https://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.5-i386-v20140311.box

Default machine specifications:
<ul>
    <li>1G RAM</li>
    <li>1CPU</li>
</ul>

# Installation
Run the following to clone the repo into your project folder<br/>
```
$git clone https://github.com/WEBIDIA/webidia-vagrant-whmcs .
```
If you want to use root login without password, create authorized_keys file in puppet/modules/users/files/authorized_keys

Run<br/>
```
$vagrant up
```

The machine runs on the same IP address and under same directory, so if you have multiple developers you can work locally using a single license.

Machine is running on <b>192.168.56.101</b> and with hostname <b>whmcs.dev</b>

You can test the server was setup correctly by navigating to http://whmcs.dev

If not you may need to manually add the following to your hosts file 
```
192.168.56.101 whmcs.dev www.whmcs.dev
```

# Database
Connect to the mySQL database via SSH using software like Sequel Pro using the following settings:
```json
{
    database_host: "127.0.0.1"
    username: "whmcs"
    password: "whmcs"
    database_name: "whmcs_db"
    SSH_host: "whmcs.dev"
    SSH_User: "vagrant"
    SSH_Password "vagrant"
}
```

Download the latest version of WHMCS from http://whmcs.com 

Installation instructions can be found at http://docs.whmcs.com/Installing_WHMCS#Installing_WHMCS