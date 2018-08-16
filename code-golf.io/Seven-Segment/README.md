<h1>Seven Segment</h1>
<b>Category:</b> Medium
<br><br>

> Using pipes and underscores print the argument as if it were displayed on a seven segment display.

> For example the number 0123456789 should be displayed as:

```
 _     _  _     _  _  _  _  _
| |  | _| _||_||_ |_   ||_||_|
|_|  ||_  _|  | _||_|  ||_| _|
```

<h2>Write-up</h2>

<h3>Python, 236 bytes</h3>


```Python
import sys
f=s=t='';a=' ';b='|'
for y in map(int,sys.argv[1]):f+=(a*3,' _ ')[y!=1and y!=4];s+=(b,a)[y%6==1or 4>y>1];s+=('_',a)[y%6==1or y<1];s+=(b,a)[7>y>4];t+=(b,a)[y%2==1or y==4];t+=('_',a)[y%3==1];t+=(b,a)[y==2]
print(f,s,t,sep='\n')
```

<b>Ungolfed:</b>

```Python
import sys
f = s = t = ''
a = ' '
b = '|'
for y in map(int, sys.argv[1]):
    f += (a * 3, ' _ ')[y != 1 and y != 4]
    s += (b, a)[y % 6 == 1 or 4 > y > 1]
    s += ('_', a)[y % 6 == 1 or y < 1]
    s += (b, a)[7 > y > 4]
    t += (b, a)[y % 2 == 1 or y == 4]
    t += ('_', a)[y % 3 == 1]
    t += (b, a)[y == 2]
print(f, s, t, sep='\n')
```

[EXPLANATION]