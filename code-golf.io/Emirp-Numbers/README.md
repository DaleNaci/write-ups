<h1>Emirp Numbers</h1>
<b>Category:</b> Easy
<br><br>

> An emirp (prime spelled backwards) is a prime number that results in a different prime when its decimal digits are reversed. For example both 13 and 31 are emirps.

> Print all the emirp numbers from 1 to 1000 inclusive, each on their own line.

<h2>Write-up</h2>

<h3>Python, 104 bytes</h3>


```Python
for n in range(999):k=int(str(n)[::-1]);(n-k)*all(n%j*(k%j) for j in range(2,k+n)if k!=j!=n)and print(n)
```

<b>Ungolfed:</b>

```Python
for n in range(999):
    k = int(str(n)[::-1])
    (n - k) * all(n % j * (k % j) for j in range(2, k + n) if k != j != n) and print(n)
```


DESCRIPTION