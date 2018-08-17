<h1>Emirp Numbers</h1>
<b>Category:</b> Easy
<br><br>

> An emirp (prime spelled backwards) is a prime number that results in a different prime when its decimal digits are reversed. For example both <b>13</b> and <b>31</b> are emirps.

> Print all the emirp numbers from <b>1</b> to <b>1000</b> inclusive, each on their own line.

<h2>Write-up</h2>

<h3>Python, 103 bytes</h3>


```Python
for n in range(999):k=int(str(n)[::-1]);(n-k)*all(n%j*(k%j)for j in range(2,k+n)if k!=j!=n)and print(n)
```

<b>Ungolfed:</b>

```Python
for n in range(999):
    k = int(str(n)[::-1])
    (n - k) * all(n % j * (k % j)for j in range(2, k + n) if k != j != n) and print(n)
```

I start with `for n in range(999)` to loop through every number from 1 to 998. If I put 1000, it would take up another character, and 999 and 1000 aren't emirp numbers so I do not have to worry about that.

`k = int(str(n)[::-1])` creates a variable `k` that reverses the number. `str(n)` turns it into a string. `[::-1]` reverses it, and `int()` turns it back into an integer.

The third line is a lot to digest, so let's break this into pieces, starting with the for loop in the center. `for j in range(2,k+n)` I am looping through every number from 2 to `k+n` to check for divisibility.

I then check that `k!=j!=n`. I check `k` because I don't want to check for divisibility from itself. I check for `j!=n` because a number is not an emirp if the reverse of the number is the same number.

If the `if` statement is true, then I head back to `n%j*(k%j)`. I am checking that both `n` and `k` are not divisible by `j`.

In Python, `all()` checks that entire list evaluates to true. If they do, `all()` will evaluate to true. If even a single value is false, then `all()` will evaluate to false. In this program, I am checking that every time we do `n%j*(k%j)`, it evaluates to a non-zero value, because `0==false` in Python.

I also have `(n-k)*` at the beginning because the two number cannot be equal to each other. If the numbers are equal to each other, we will be multiplying the entire `all()` statement by 0, making the entire statement false, so the `print(n)` will never run.