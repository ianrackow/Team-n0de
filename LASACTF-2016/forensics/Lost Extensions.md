<b>Problem:</b><br>
This file got sad and threw away its extension! Maybe you can figure out what it's supposed to be? <br>Hint: There sure are a lot of numbers there.<br><br>

<b>Solution:</b><br>
This problem involved a bit of common sense, but my biggest asset was my search engine.<br><br>

<b>Step 1: Extensions.exe</b><br>
As for many basic forensics problems, the first step I took was opening the file in a hex editor. I was met with the familiar file signiture of zip files: PK. I knew right away that this was a zip file from past experience, but a quick google search reveals that the file signiture is indeed of a zip file. The file can then be unzipped by manually changing the file extension to .zip and unzipping or by using the unzip command on terminal. Unzipping the file leaves an extensionless file called "I'mLost ;(".<br><br>

<b>Step 2: Figuring out the Lost Extension</b><br>
Again, I opened the file in a hex editor. Inside lie a multitude of numbers with the occasional "v", "vn", or "f" mixed in. The first result from a google search of "v vn f" reveals that the file is a .obj file (and that the numbers represent (x,y,z) cooridinates and other 3D properties).<br><br>

<b>Step 3: Opening the file</b><br>
I then used a online 3D viewer (https://www.3dvieweronline.com/) to try to open the file. One spam email (just in case) and free trial later, I opened the file and found the flag inside constructed using 3D letters.<br><br>

flag: lasactf{wh0_n33ds_3xt3nsions}
<br><b>by Josh (B@man)</b>
