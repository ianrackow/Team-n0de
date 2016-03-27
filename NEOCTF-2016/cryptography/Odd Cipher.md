<b>Problem:</b><br>
nukr{JAxhUWVEkdJp}<br>
Need to mention, there are numbers in the flag, and also, there is an underscore in the 11th character of the flag. Shoutout to 
team n0de for solving this problem without this information somehow :).<br>
Hint: Should come out to be a readable phrase<br><br>
<b>Solution:</b><br>
:/, this is an odd cipher. If you observe how the first 4 characters relate to 'flag', you'll notice that the shifting increment increases by 1 every time. How odd.<br>
Of course, what's odder is that sometimes the letters will shift back to the end of their corresponding upper/lowercase alphabet, or they'll shift to a number or underscore.<br>
To fix that, just edit the program below [whether or not it cycles] and find the readable combination of the outputs. Voila.<br><br>
```python
def shift(n,s):
	if ord(n) > 96 and ord(n) - s < 97:
		return chr(ord(n)-s+26)
	elif ord(n) > 64 and ord(n) - s < 48:
		return chr(ord(n)-s+26)
	return chr(ord(n)-s)
flag = 'nukr{JAxhUWVEkdJp}'
message = ''
step = 8
for char in flag:
	message += shift(char,step)
	step += 1
print(message)
```
<br>
flag: flag{W3irD_C1ph3r}<br>
<b>by defund </b><br>
Note: This is the sort of challenge where you can't think that much while solving it; I did it half asleep on the schoolbus.

