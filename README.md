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
jshunter -l js.txt -t 10 | tee -a jshunteroutput.txt [Edit js hunter tool with new regex] [https://github.com/KaioGomesx/JSScanner/blob/main/regex.txt]
```
```sql
nuclei -l js -t /home/nazmul/nuclei-templates/http/exposures -stats -j -o nuclei-js-output.json -c 50 -rl 500 -bs 50 -timeout 10 -retries 1
```
```sql
filepicker_key api docs curl
```
