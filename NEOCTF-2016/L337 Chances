<b>Problem:</b><br>
How Lucky Are You?<br>
162.243.0.171/Chance.html<br><br>
<b>Solution:</b><br>
The website's source shows that it is accessing a php page every time you visit. Judging from the title, it looks like this php page will very rarely give you the actual flag. Make a little script to continually access this php page until you get the correct flag.<br><br>
```python
import urllib2
html = 'neoflag{NOT_THE_FLAG}'
while 'neoflag{NOT_THE_FLAG}' in html:
	response = urllib2.urlopen('http://162.243.0.171/secret.php/')
	html = response.read()
print(html)
```
<br>
flag: flag{T0O_M@ny_But10ns}
<b>by defund

