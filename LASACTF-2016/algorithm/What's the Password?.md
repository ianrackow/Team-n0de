<b>Problem:</b><br>
A login system asks for 10 random characters from a password. For example, "What are the 2nd, 6th, 23rd, .... characters?" The characters are always asked in the order that they appear in the password. Here is a list of 250 successful logins for an account. Find the shortest possible password that could fulfill all these logins. <br>Note: Flag not in LASACTF{} format<br><br>
<b>Solution:</b><br>
If you observe the substrings, no character appears twice in the same line. Assuming that there are no repeats in the password, you can execute this code, where ```a``` contains the substrings read from the text file. Avoid that shortest common superstring dp crap. Voila.<br><br>
```python
a = a.split()
a = [[c for c in x] for x in a]
r = []
for i in range(len(a)):
    for j in range(len(a[i])):
        if a[i][j] not in r:
            r.append(a[i][j])
unordered = True
while unordered:
    unordered = False
    for i in range(len(a)):
        for j in range(1,len(a[i])):
            for c in a[i][0:j]:
                if r.index(c)>r.index(a[i][j]):
                    r = r[:r.index(a[i][j])]+\
                        [c]+\
                        [a[i][j]]+\
                        r[r.index(a[i][j])+1:r.index(c)]+\
                        r[r.index(c)+1:]
                    unordered = True
f = ''.join(r)
print(f)
```
<br>
flag: ,oJVcQ)u!4P5%&}@+F:;`|*3rBRvDAs?pfM2qE7_k{Gm/=i<^b<br>
<b>by defund</b>

