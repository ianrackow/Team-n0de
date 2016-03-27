<b>Problem:</b><br>
There is a flag hidden somewhere in the dungeon<br><br>
<b>Solution:</b><br>
This problem was pretty straightforward, except for installing a stupid python qrcode module. I didn't want to deal with some random zbar crap, so I just downloaded some library stuff on kali. Strangely, in 3 of the qrcodes, the program decoded the message to be a series of numbers [???], so that's what part of the code is for; I just manually decoded those 3. Whatever, you know. After 100 qrcodes, the program spit out the flag. Voila.<br><br>
```
sudo apt-get install librsvg2-bin
sudo apt-get install python-qrtools
```
```python
import os, qrtools
url = 'web.lasactf.com:63017/21GKUIXGSULUQJEKRAKTWZJYLFSTJQFK.svg'
while 'web.lasactf.com:63017' in url:
	link = url
	os.popen('curl http://'+url+' > qr.svg')
	os.popen('rsvg-convert -f png -o qr.png qr.svg')
	qr = qrtools.QR()
	qr.decode('qr.png')
	os.popen('rm qr.svg')
	os.popen('rm qr.png')
	print(qr.data)
	url = str(qr.data)
print(url)
f = open('link.txt','w')
f.write('http://'+link)
f.close()
```
<br>
<b>Alternate Solution:</b><br>
100 qrcodes isn't that much. Take two phones with a qrdecoder. You know what to do. :D
<br>
flag: lasactf{a_long_tw1sted_maz3}<br>
<b>by defund</b>

