<h1>Emirp Numbers</h1>
<b>Category:</b> Easy
<br><br>

> An emirp (prime spelled backwards) is a prime number that results in a different prime when its decimal digits are reversed. For example both 13 and 31 are emirps.

> Print all the emirp numbers from 1 to 1000 inclusive, each on their own line.

<h2>Write-up</h2>

<h3>Python, 58 bytes</h3>


```Python
for i in range(999):
    x=int(str(i)[::-1])
    if all(i%j for j in range(2,i))and all(x%j for j in range(2,x))and x!=i:print(i)
```

<b>Ungolfed:</b>

```Python
for i in range(999):
    x = int(str(i)[::-1])
    if all(i % j for j in range(2, i)) and all(x % j for j in range(2, x)) and x! = i:
        print(i)
```


DESCRIPTION