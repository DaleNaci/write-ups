<h1>Fizz Buzz</h1>
<b>Category:</b> Easy
<br><br>

> Print the numbers from <b>1</b> to <b>100</b> inclusive, each on their own line.

> If, however, the number is a multiple of <b>three</b> then print <b>Fizz</b> instead, and if the number is a multiple of <b>five</b> then print <b>Buzz</b>.

> For numbers which are multiples of <b>both three and five</b> then print <b>FizzBuzz</b>.

<h2>Write-up</h2>

<h3>Javascript, 90 bytes</h3>


```Javascript
for(var i=1;i<101;i++){var s=''
if(i%3==0)s='Fizz'
if(i%5==0)s+='Buzz'
if(!s)s=i
print(s)}
```

<b>Ungolfed:</b>

```Javascript
for(var i = 1; i < 101; i++)
{
    var s = ''
    if(i % 3 == 0)
        s = 'Fizz'
    if(i % 5 == 0)
        s += 'Buzz'
    if(!s)
        s = i
    print(s)
}
```

For this program, I start with a single for loop to loop through 1-100. I use this blank `s` variable so that I don't need a separate if statement for checking if the answer is 'FizzBuzz.' `if (i%3==0)` and `if (i%5==0)` both check if there are multiples of 3 and 5, respectively. Since `i%3` comes before `i%5`, s will correctly be set to 'FizzBuzz' if both are applicable.

<h3>Python, 93 bytes</h3>


```Python
for i in range(1,101):
    s=''
    if i%3==0:s='Fizz'
    if i%5==0:s+='Buzz'
    if not s:s=i
    print(s)
```

<b>Ungolfed:</b>

```Python
for i in range(1,101):
    s=''
    if i % 3 == 0:
        s = 'Fizz'
    if i % 5 == 0:
        s += 'Buzz'
    if not s:
        s = i
    print(s)
```

Same explanation as the Javascript program, but unfortunately contains 3 more characters.

<h3>Perl 6, 101 bytes</h3>

```Perl
for ^100+1 ->$i {if !($i%3) {"Fizz".print}
if !($i%5) {"Buzz".print}
if $i%3&$i%5 {$i.print}
''.say;}
```

<b>Ungolfed:</b>

```Perl
for ^100 + 1 -> $i
{
    if !($i % 3)
    {
        "Fizz".print
    }
    if !($i % 5)
    {
        "Buzz".print
    }
    if $i % 3 & $i % 5
    {
        $i.print
    }
}
```

This also loops from 1-100. The `if` statements check for divisibility, and the third one prints if both results do not go to 0. The first two `if` statement conditionals serve as double negatives, saying "if i % 3 (or i % 5) is NOT equal to 0".