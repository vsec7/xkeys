# xkeys

A eXtractor sensitive Keys, Secret, Token or interested things from source.

## Install
```
 ▶ go get -u github.com/vsec7/xkeys
```

## Basic Usage

```
 ▶ xkeys --help 

xKeys (eXtract Keys)

By     : viloid [Sec7or - Surabaya Hacker Link]

Basic Usage :
 ▶ echo http://domain.com/path/file.js | xkeys
 ▶ cat listurls.txt | xkeys -o cans.txt

Options :
  -H, --header <header>                 Header to the request
  -o, --output <output>                 Output file (*default xkeys.txt)
  -x, --proxy <proxy>                   HTTP proxy
  -w, --wordlist <wordlist>             Custom wordlists keyword pattern
  -k, --key <keyword>                   Custom single keyword pattern
  -t, --telegram <BotToken|RecipientID> Telegram notification

```

## Advanced Usage
```
Custom single keyword with send notification telegram e.g :
 ▶ echo http://domain.com/path/file.js | xkeys -k "access_token" -t "26525265:IniBotTelegramToken|86565765"

Custom list keywords e.g : 
 ▶ cat listurls.txt | xkeys -w customkeywordlist.txt -H "Authorization: Bearer eXAmPLe" -H "Cookie: ExAmpLe" -o xkeys-domain.txt

** URLs in listurls should contains http:// or https:// 

 ▶ cat listurls.txt
http://domain.com/path/file.js
http://domain.com/path/file2.js
http://domain.com/path/file3.js
...

** customkeywordlist.txt contains your custom keyword list (delim newline) **

 ▶ cat customkeywordlist.txt
access_token
secret_key
...
```

## Possible Value Extraction
```
{keyword}=<value>
{keyword}= <value>
{keyword} = <value>
'{keyword}'='<value>'
'{keyword}'= '<value>'
'{keyword}' = '<value>'
"{keyword}"="<value>"
"{keyword}" = "<value>"
"{keyword}":"<value>"
"{keyword}" :"<value>"
"{keyword}" : "<value>"
{keyword}=<value>&
```

## Default Keywords
Check main.go in function *keywords()*

```
Code Snip:

func keywords() []string {
	return []string{
		"access_key",
		"access_token",
		"..."
		"..."
	}
}
```

## Credit And Thanks
```
@tomnomnom (github.com/tomnomnom)
@bhrdn (github.com/bhrdn)
```