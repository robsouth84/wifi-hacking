# wifi-hacking


## wifite
I use wifite version in ubuntu repos with a [patch](https://github.com/robsouth84/wifite/blob/master/wifite.py), but will probably checkout [v2](https://github.com/derv82/wifite2) soon 

### interactive scan:
This will allow selection of network, automatic collection of handshakes (with de-auths), and *should* crack with given wordlist 
```bash
sudo wifite --crack -dict rockyou.txt
```






## aircrack-ng 
Before wifite (and also before I patched wifite) aircrack-ng was the way to go.  Now wifite handles all of the hard work, but for demo's the aircrack-ng screen is always more fun :)

### interactive scan:
Given a bssid, a decent [wordlist](https://wiki.skullsecurity.org/Passwords), and a capture file.  This should find the wifi password (assuming its in the word list)
```bash
sudo aircrack-ng -b xx:xx:xx:xx:xx:xx -l xxNet-Cracked-PW.txt capture_file_with_handshake.cap -w rockyou.txt 
```




## Wordlists
[skull security](https://wiki.skullsecurity.org/Passwords)
[packet storm](https://packetstormsecurity.com/Crackers/wordlists/)
[Daniel Miessler](https://github.com/danielmiessler/SecLists/tree/master/Passwords)


### Other Interesting Links
[NIST Bad Passwords](https://cry.github.io/nbp/)
