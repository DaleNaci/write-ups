<h1>Fibonacci</h1>
<b>Category:</b> Easy
<br><br>

> Print the first <b>31</b> Fibonacci numbers from <b>F0 = 0</b> to <b>F30 = 832040</b> (inclusive), each on a separate line.

<h2>Write-up</h2>

<h3>Python, 41 bytes</h3>


```python
x,y=0,1
for i in[1]*31:print(x);y,x=y+x,y
```

<b>Ungolfed:</b>

```python
x = 0
y = 1
for i in [1]*31:
	print(x)
	y, x = y + x, y
```

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


