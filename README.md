Multiple Tools For Subdomain Enumeration:-


You need to install the required tools and add your API keys:-

https://github.com/OWASP/Amass/blob/master/doc/install.md
https://github.com/projectdiscovery/chaos-client
https://github.com/projectdiscovery/subfinder
https://github.com/tomnomnom/assetfinder
https://github.com/Findomain/Findomain
https://github.com/gwen001/github-subdomains
https://github.com/Cgboal/SonarSearch
https://github.com/projectdiscovery/httpx
https://github.com/projectdiscovery/nuclei
https://github.com/projectdiscovery/nuclei-templates
https://github.com/emadshanab/Nuclei-Templates-Collection




amass enum -d google.com -config /root/.config/amass/config.ini -o amass3 ; chaos -d google.com -o chaos3  ; subfinder -d google.com -all -o subfinder3 ; findomain -t google.com -q -u findomain3 ; github-subdomains -d google.com-o github-subdomains3 ; crobat -s google.com -u >> corbat3 ; cat  subfinder3 chaos3 amass3 findomain3 corbat3 | sort -u >> hosts3 ;  httpx -l hosts3 -threads 9000  | anew domains3 ; rm -rf hosts3 amass3 chaos3 subfinder3 findomain3 github-subdomains3 corbat3 ; nuclei -c 100 -l domains3 -t /root/nuclei-templates/  -o domains3_results.txt
