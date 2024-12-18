## All About JavaScript Analysis For Bug Bounty Hunting

```sql
subfinder -dL target.txt -all -recursive -o Subs01.txt
```
```sql
subenum -l target.txt -u wayback,crt,abuseipdb,bufferover,Findomain,Subfinder,Amass,Assetfinder -o Subs02.txt
```
```sql
cat Subs*.txt | anew | tee AllSubs.txt
```
```sql
cat AllSubs.txt | httpx -o AliveSubs.txt
```
```sql
cat AliveSubs.txt | waybackurls | tee urls01.txt
```
```sql
cat AliveSubs.txt | hakrawler -d 10 | tee urls02.txt
```
```sql
katana -list AliveSubs.txt -d 10 | tee urls03.txt
```
```sql
cat urls*.txt | anew | tee urls.txt
```
```sql
cat urls.txt | grep -iE '.js' | grep -ivE '.json'| sort -u | tee js01.txt
```
```sql
cat urls.txt | subjs | tee js02.txt
```
```sql
find javascript file from BURPSUITE | tee js03.txt
```
```sql
cat js*.txt | uro | tee js.txt
```
```sql
grep -r -E "aws_access_key|aws_secret_key|api key|passwd|pwd|heroku|slack|firebase|swagger|aws_secret_key|aws key|password|ftp password|jdbc|db|sql|secret jet|config|admin|pwd|json|gcp|htaccess|.env|ssh key|.git|access key|secret token|http://1|http://2|http://3|http://4|http://5|http://6|http://7|http://8|http://9|oauth_token|oauth_token_secret" js.txt
```
```sql
https://github.com/streaak/keyhacks
```
```sql
jshunter -l js.txt -t 10 | tee -a jshunteroutput.txt [Edit js hunter tool with new regex] [https://github.com/KaioGomesx/JSScanner/blob/main/regex.txt]
```
```sql
nuclei -l js -t /home/nazmul/nuclei-templates/http/exposures -stats -j -o nuclei-js-output.json -c 50 -rl 500 -bs 50 -timeout 10 -retries 1
```
```sql
filepicker_key api docs curl
```
<hr>

```powershell
httpx -l AliveSubs.txt -p 66,80,81,443,445,457,1080,1100,1241,1352,1433,1434,1521,1944,2301,3000,3128,3306,4000,4001,4002,4100,5000,5432,5800,5801,5802,6346,6347,7001,7002,8000,8080,8443,8888,30821 -fr -x GET,POST -t 200 -rl 500 -timeout 5 -retries 1 -stats -o portfuzzing-results.txt
```
```sql
python3 /home/nazmul/subowner/subowner.py -f AllSubs.txt -t 20
```
```sql
subzy run --targets AllSubs.txt --vuln --output subzy.txt
```
