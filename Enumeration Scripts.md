nmap -Pn {IP ADDR}
 nmap -sC -sV -O -oA nmap/{ctf-name} {IP ADDR}
- -sC : Default scripts
- -sV : Version detection
- -oN : Output to be stored in the directory ‘nmap’ you created earlier
- -O : 
- -oA : 