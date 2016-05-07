# Vagrant/Puppet setup for WHMCS 6
Vagrant/Puppet configuration for WHMCS 6 installation

Based on CentOS 6.5 <br/>
https://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.5-i386-v20140311.box

Default settings:
<ul>
    <li>1G RAM</li>
    <li>1CPU</li>
</ul>

# Installation
Clone repo to project folder<br/>
```
$git clone https://github.com/WEBIDIA/webidia-vagrant-whmcs .
```
If you want to use root login without password, create authorized_keys file in puppet/modules/users/files/authorized_keys

Run<br/>
```
$vagrant up
```

In about 4-5 minutes your vagrant machine would be ready to run.

Machine is always running on same IP and under same directory, so if you have developers license,
there should be no issues with licenses IP/Location change, even with multiple developers working on project

Machine is running on <b>192.168.56.101</b> and with hostname <b>whmcs.dev</b>

You will have to add 
```
192.168.56.101 whmcs.dev www.whmcs.dev
```
To your hosts file in order to easily access it from browser.


Connect to the mySQL database via SSH using software like Sequel Pro using the following settings:
```json
{
    mySQL_host: "127.0.0.1"
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