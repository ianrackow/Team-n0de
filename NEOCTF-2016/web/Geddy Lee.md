<b>Problem:</b><br>
Ah, time to work on a fresh app. Got my coffee, got my music... wait, who is that???!!<br>
104.131.43.243:40000/<br><br>
<b>Solution:<\b><br>
Upon seeing the problem title, I noticed the problem title refers to the lead singer of the Canadian rock group, Rush. 
Sadly, the problem had nothing to do with Rush, which is easily discovered by navigating to the site given in the problem description.
On the site, we are given what appears to be a homepage of some sort of website using "Geddy".
With a quick google search finding the link http://geddyjs.org/, it is discovered that Geddy is a web framework for Node.js.
At this point, no obvious pathway to solving was apparent, so I decided to take a look around the site we are provided with.
The site contains only a few pages, most linking to help on an outside Geddy site. Looking at the source for the main page hosted on
104.131.43.243:40000 provides no useful information. It was here that I got a bit stuck, but after a while I decided that there must be
some other page on the site. Not knowing how to find it, I started with a google search for "Geddy file directory".
The second link found, https://nodesecurity.io/advisories/geddy-directory-traversal, shows a method of getting the static directory
of a Geddy app. <br><br>

<b>Overview<\b><br>
Geddy static file serving allows directory traversal with a URI encoded path.<br>
Example: http://localhost:4000/..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2fetc/passwd <br><br>

A little more research on what this does shows that Geddy applications have a vulnerability which causes them to serve a static file when
the URL route is not matched on the server. With this in mind, we try that URL path with the link provided in the problem: <br>
104.131.43.243:40000/..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2fetc/passwd<br>
Upon entering this link, a file is immediately downloaded onto my computer named passwd. Looking through passwd in a text editor reveals 
the last string which happens to be our flag.<br>
flag: flag{2112_slappa_da_BASS}<br>
<b> by Ian <\b>







