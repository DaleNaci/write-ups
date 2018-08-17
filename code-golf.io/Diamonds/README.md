<h1>Diamonds</h1>
<b>Category:</b> Medium
<br><br>

> Print a size ascending range of Diamonds using the numbers 1 to 9, ranging from size 1 to size 9, each diamond separated by a blank line.

> A size 1 diamond should look like this, a single centered 1:

```
1
```

> With the largest size 9 diamond looking like this:

```
         1
        121
       12321
      1234321
     123454321
    12345654321
   1234567654321
  123456787654321
 12345678987654321
  123456787654321
   1234567654321
    12345654321
     123454321
      1234321
       12321
        121
         1
```

<h2>Write-up</h2>

<h3>Perl 6, 133 bytes</h3>


```Perl
my $a=&abs;for ^9 -> $i {for -$i…$i+1 -> $j {print(' 'x($j.$a+9-$i));for $j.$a-$i..$i-$j.$a -> $k {print($i-$j.$a-$k.$a+1);};say();}}
```

<b>Ungolfed:</b>

```Perl
my $a = &abs;
for ^9 -> $i
{
    for -$i…$i + 1 -> $j
    {
        print(' ' x ($j.$a + 9 - $i));
        for $j.$a - $i..$i - $j.$a - > $k
        {
            print($i - $j.$a - $k.$a + 1);
        };
        say();
    }
}
```

Diamonds has a relatively large amount of math logic going into it, at least for my solution.
`my $a = &abs;` sets up the abs function to be called when I type $a, saving a few characters since I use absolute value a lot.

`for ^9 -> $i` is a for loop for each diamond, printing 9 in total.

`for -$i…$i+1 -> $j` is a for loop which totals to `($i*2) + 1`.

`print(' 'x($j.$a+9-$i))` prints out the number of spaces taking the absolute value of the inner for loop value `$j`, adds 9, and then subtracts the outer for loop value, `$i`, which references to the diamond number.

`for $j.$a-$i..$i-$j.$a -> $k` is a third inner for loop for printing the numbers that make up the diamond. We take the absolute value for `$j` and subtract `$i`, and then go all the way to `$i` subtracted by the absolute value of `$j`, which is the opposite of the beginning of the for loop.

`print($i-$j.$a-$k.$a+1)` prints the numbers for each diamond. We take `$i`, subtract the absolute values of `$j` and `$k`, and add 1 so that it starts at 1 instead of 0.

`say()` adds the line break;

<h3>Python, 152 bytes</h3>


```Python
p,r,a=print,range,abs
for i in r(1,10):
    for j in r(-i+1,i):
        p(' '*(a(j)+10-i),end='')
        [p(i-a(j)-a(k),end='')for k in r(a(j)+1-i,i-a(j))]
        p()
    p()
```

<b>Ungolfed:</b>

```Python
for i in range(1, 10):
    for j in range(-1 + 1, i):
        print(' ' * (abs(j) + 10 - i), end='')
        for k in range(abs(j) + 1 - i, i - abs(j)):
            print(i - a(j) - a(k), end='')
        print()
    print()
```


This solution is just a longer version of the Perl 6 solution, but I will add an explanation simply because of the length of the code.

`p,r,a=print,range,abs` sets up the print, range, and abs functions to be called so that it will have a shorter number of characters used overall for calling each function.

`for i in r(1,10)` is a for loop for each diamond, printing 9 in total.

`for j in r(-1+1,i)` is a for loop which totals to `(i*2) + 1`.

`p(' '*(a(j)+10-i),end='')` this prints the spaces that go before each line of the diamond. I am taking the absolute value of `j`, starting at 10, and subtracting `i` at the end.

`for k in range(abs(j)+1-i,i-abs(j))` is a third inner for loop for printing the numbers that make up the diamond. We take the absolute value for `j`, add `1`, and subtract `i`, and then go all the way to `i` subtracted by the absolute value of `j`, which is the opposite of the beginning of the for loop.

`print(i-a(j)-a(k),end='')` prints the numbers for each diamond. We take `i` and subtract the absolute values of `j` and `k`.

the two `print()` statements at the bottom are for the line breaks.