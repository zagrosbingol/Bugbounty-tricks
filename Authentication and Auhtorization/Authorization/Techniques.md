1. Classic IDOR:
- Create two accounts
- one is zaggeb and other is zaggeb2
- Note the ID of zaggeb2, can be anything such as UUID, ID, cookie based ID.
- Navigate with burp to different pages and change youre own ID to zaggeb2 ID.
- See if any info or anything else popup.
--> See payload types for different bypasses.


2 Registration leads to a certain page that looks like a path:

Lets say for example, you register zaggeb and when you are finished, you get to a page like this:
domain.com/zaggeb

Try changing username to:
images_zaggeb

Results:
domain.com/images_zaggeb
Use encoding for slashes


3. Use .JSON after url to unmask parameters when inspect element does not work:
Append .json to the end of url and see it it works to unmask details.


4. Ruby on rails attacks:
Ruby-on-Rails enforces "convention" over "configuration" which really helps to guess class names and attributes' name...

Identification signs:
The first part is the table name and the second part in the brackets is the key.
See: https://pentesterlab.com/exercises/autho_06/course
username[user] =
password[Password] =

 4.1 Mass assignments Overwriting arbitrary parameters:
 - Review firstly the source code and see what parameters exist
 - Continue by making a form request, add new parameters that were found in the source code to manipulate the query. This includes new tables and keys
 
