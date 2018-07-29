<h1>Prime Numbers</h1>
<b>Category:</b> Easy
<br><br>

> Print all the prime numbers from 1 to 100 inclusive, each on their own line.

<h2>Write-up</h2>

<h3>Perl 6, 37 bytes</h3>


```Perl
print "$_\n"for ^99 .grep: *.is-prime
```

<b>Ungolfed:</b>

```Perl
print "$_\n" for ^99 .grep: *.is-prime
```


In all honesty, I am not sure how this program works. On <a href="https://perl6.org/">Perl 6's Front Page</a>, they have a "Lazy Evaluation" section where they have a way to generate an infinite list of primes: `my @primes = ^∞ .grep: *.is-prime;`. I changed it around a bit to be a print statement, changed the infinity symbol to be ^99, and thus my solution was born.

<h3>Python, 63 bytes</h3>


```Python
[print(i) for i in range(2,100)if all(i%j for j in range(2,i))]
```

<b>Ungolfed:</b>

```Python
for i in range(2, 100):
    if all(i % j for j in range(2, i)):
    	print(i)
```


For this program, we have one regular for loop, and one weird for loop. The outer for loop just loops through the numbers 2-100 to check if each number looped through is prime. For the if statement, `i % j for j in range(2, i)` goes through each number and checks whether it is divisible by any of the numbers before it (besides 1). The all() checks every iteration of the for loop, and only evaluates as true if all of the iterations inside it (so every for loop) happens to be true. If it is true, it will print out the number.