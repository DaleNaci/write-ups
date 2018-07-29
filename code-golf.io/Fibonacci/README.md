<h1>Fibonacci</h1>
<b>Category:</b> Easy
<br><br>

> Print the first <b>31</b> Fibonacci numbers from <b>F0 = 0</b> to <b>F30 = 832040</b> (inclusive), each on a separate line.

<h2>Write-up</h2>

<h3>Python, 41 bytes</h3>


```Python
x,y=0,1
for i in[1]*31:print(x);y,x=y+x,y
```

<b>Ungolfed:</b>

```Python
x = 0
y = 1
for i in [1]*31:
	print(x)
	y, x = y + x, y
```


For Fibonacci, I was in a constant battle about whether to use recursion or a for loop. I initially had a 49 byte Python recursion solution, but this for loop solution ended up being a lot quicker. This program uses 2 variables, `x` and `y`. They initially start at `0` and `1`, similar to an actual fibonacci sequence.

`for i in[1]*31` is a shorter version of writing range(31), and can be used if you do not actually need `i` for anything. It is looping through a list of 31 1's.

I initially had a `temp` variable to make a triple swap, but I just defaulted to that because that's what I use in Java. I later learned that in Python, you can swap the value of two variables using `a,b=b,a`, so I took out my temp variable and used `y,x=y+x,y` instead.

<h3>Perl 6, 59 bytes</h3>


```Perl
my $f=->$i,$j {$i.say;if $j <832041 {$f($j,$i+$j)}};$f(0,1)
```

<b>Ungolfed:</b>

```Perl
my $f = -> $i, $j
{
    $i.say;
    if $j < 832041
    {
        $f($j, $i + $j);
    }
};
$f(0, 1);
```

Unlike my Python solution, I used recursion for my Perl 6 solution. I define a function with two variables, and until I reach the 832041 limit. I use `$f($j, $i + $j)` for the recursion variable swap. This has the same effect as the `y,x=y+x,y` variable swap in the Python program.

<h3>Javascript, 72 bytes</h3>


```Javascript
x=0;y=1;print('0\n1');for(let i=0;i<29;i++){temp=y;y+=x;x=temp;print(y)}
```

<b>Ungolfed:</b>

```Javascript
x = 0;
y = 1;
print('0\n1');
for (let i = 0; i < 29; i++)
{
    temp = y;
    y += x;
    x = temp;
    print(y);
}
```

This is similar to the Python program with the for loop, but we have to use a `temp` variable and perform a triple swap instead. We also added an extra print statement at the beginning because of the limits of our program.