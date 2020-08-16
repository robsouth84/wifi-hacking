# wifi-hacking


## wifite
I use wifite version in ubuntu repos with a [patch](https://github.com/robsouth84/wifite/blob/master/wifite.py), but will probably checkout [v2](https://github.com/derv82/wifite2) soon 


### Passive Scanning:
I'm not sure this is possible with wifite. It seems to deauth automatically which is nice as long as you are allowed to use this method.

### Interactive Scan:
This will allow selection of network, automatic collection of handshakes (with de-auths), and *should* crack with given wordlist 
```bash
sudo wifite --crack -dict rockyou.txt
```




### Targetted Scan:
This will search for a specific network and if found jump right into looking for handshake captures without any user interaction.  However, if specified network is not found, wifite will fall back to an interactive scan

#### bssid (MAC) search
```bash
sudo wifite -b <MAC in form of xx:xx:xx:xx:xx:xx>
```
#### essid (Network Name) search
special chars may cause issues
```bash
sudo wifite -e <SSID string>
```




## aircrack-ng 
Before wifite (and also before I patched wifite) airodump-ng & aircrack-ng were the way to go.  Now wifite handles all of the hard work, but for demo's the aircrack-ng screen is always more fun :)

Given a bssid / essid, a decent [wordlist](https://github.com/robsouth84/wifi-hacking/blob/master/README.md#wordlists), and a capture file.  This should find the wifi password (assuming its in the word list) and save it to a text file

#### bssid (MAC) search
```bash
sudo aircrack-ng -b xx:xx:xx:xx:xx:xx -l Cracked-PW.txt capture_file_with_handshake.cap -w rockyou.txt 
```

#### essid (Network Name) search
Might run into issues with special characters
```bash
sudo aircrack-ng -e "PrettyFly4aWiFi" -l Cracked-PW.txt capture_file_with_handshake.cap -w rockyou.txt 
```



## Wordlists

* [skull security](https://wiki.skullsecurity.org/Passwords)
* [packet storm](https://packetstormsecurity.com/Crackers/wordlists/)
* [Daniel Miessler](https://github.com/danielmiessler/SecLists/tree/master/Passwords)
* 

### Other Interesting Links
[NIST Bad Passwords](https://cry.github.io/nbp/)
