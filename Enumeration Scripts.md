nmap -Pn {IP ADDR}
 nmap -sC -sV -O -oA nmap/{ctf-name} {IP ADDR}
- -sC : Default scripts
- -sV : Version detection
- -oN : Output to be stored in the directory ‘nmap’ you created earlier
- -O : Enable OS detection
- -oA : Output the scan results in all formats (normal, XML, and grepable) to files prefixed with the specified path and filename.