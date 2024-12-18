## All About JavaScript Analysis For Bug Bounty Hunting

```cmd
 1. subfinder -dL target.txt -all -recursive -o Subs01.txt
 2. subenum -l target.txt -u wayback,crt,abuseipdb,bufferover,Findomain,Subfinder,Amass,Assetfinder -o Subs02.txt
 3. cat Subs*.txt | anew | tee AllSubs.txt
 4. cat AllSubs.txt | httpx -o AliveSubs.txt
 5. cat AliveSubs.txt | waybackurls | tee urls01.txt
 6. cat AliveSubs.txt | hakrawler -d 10 | tee urls02.txt
 7. katana -list AliveSubs.txt -d 10 | tee urls03.txt
 8. cat urls*.txt | anew | tee urls.txt
 9. cat urls.txt | grep -iE '.js' | grep -ivE '.json'| sort -u | tee js01.txt
10. cat urls.txt | subjs | tee js02.txt
11. find javascript file from BURPSUITE | tee js03.txt
12. cat js*.txt | uro | tee js.txt
13. jshunter -l js.txt -t 10 | tee -a jshunteroutput.txt [Edit js hunter tool with new regex] [https://github.com/KaioGomesx/JSScanner/blob/main/regex.txt]
14. nuclei -l js -t /home/nazmul/nuclei-templates/http/exposures -stats -j -o nuclei-js-output.json -c 50 -rl 500 -bs 50 -timeout 10 -retries 1
13. filepicker_key api docs curl
```
