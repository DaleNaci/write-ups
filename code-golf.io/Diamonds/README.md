<h1>Diamonds</h1>
<b>Category:</b> Easy
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


DESCRIPTION

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


DESCRIPTION