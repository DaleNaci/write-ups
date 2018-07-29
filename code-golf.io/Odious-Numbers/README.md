<h1>Odious Numbers</h1>
<b>Category:</b> Easy
<br><br>

> An odious number is a non-negative number that has an odd number of 1s in its binary expansion.

> Print all the odious numbers from <b>0</b> to <b>50</b> inclusive, each on their own line.

> Numbers that are not odious are called evil numbers.

<h2>Write-up</h2>

<h3>Python, 55 bytes</h3>


```Python
[print(i)for i in range(51)if str(bin(i)).count('1')%2]
```

<b>Ungolfed:</b>

```Python
for i in range(51):
    if str(bin(i)).count('1') % 2:
        print(i)
```


It starts by looping through the numbers 0 through 50. `bin` converts a number to binary. I want to use the `.count()` method to check the number of 1's in each number's binary, but `.count()` only works for strings, so I use `str()` to convert it into one. I then check if the count is divisible by 2 using `%2`, and print it if that is true.