<h1>Niven Numbers</h1>
<b>Category:</b> Easy
<br><br>

> A niven number is a non-negative number that is divisible by the sum of its digits.

> Print all the niven numbers from 0 to 100 inclusive, each on their own line.

<h2>Write-up</h2>

<h3>Python, 55 bytes</h3>


```Python
[print(i)for i in range(1,101)if i%(int(i/10)+i%10)==0]
```

<b>Ungolfed:</b>

```Python
for i in range(1, 101):
    if i % (int(i / 10) + i % 10) == 0:
        print(i)
```


I start with a for loop to go through the numbers 1 through 100. 0 is not checked because my code prohibits it, but luckily 0 is not a Niven Number. To check through each digit, I can take `i/10` and `i%10`. `i/10` takes tens place digit, and `i%10` takes the ones place digit.

I then use `i % ... 0` to check if it is divisible by the digits added together, and print if that is true.