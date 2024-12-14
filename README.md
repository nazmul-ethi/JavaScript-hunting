## All About JavaScript Analysis For Bug Bounty Hunting
```powershell

 1. subfinder -dL target.txt -all -recursive -o Subs01.txt
 2. subenum -l target.txt -u wayback,crt,abuseipdb,bufferover,Findomain,Subfinder,Amass,Assetfinder -o Subs02.txt
 3. cat Subs*.txt | anew | tee AllSubs.txt
 4. cat AllSubs.txt | httpx -o AliveSubs.txt
 5. cat AliveSubs.txt | waybackurls | tee urls01.txt
 6. cat AliveSubs.txt | hakrawler -d 10 | tee urls02.txt
 7. katana -list AliveSubs.txt -d 10 | tee urls03.txt
 8. cat urls*.txt | anew | tee urls.txt
 9. cat urls.txt | grep -iE '.js' | grep -ivE '.json'| sort -u | tee js.txt
10. filepicker_key api docs curl
```
