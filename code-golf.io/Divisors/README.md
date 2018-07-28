<h1>Divisors</h1>
<b>Category:</b> Easy
<br><br>

> A number is a divisor of another number if it can divide into it with no remainder.
> 
> Print the positive divisors of each number from 1 to 100 inclusive, on their own line, with each divisor separated by a space.

<h2>Write-up</h2>

<h3>Javascript, 76 bytes</h3>


```Javascript
for(let i=1;i<101;i++){for(let j=1;j<101;j++)if(i%j==0)write(j+" ");print()}
```

<b>Ungolfed:</b>

```Javascript
for (let i = 1; i < 101; i++)
{
	for (let j = 1; j < 101; j++)
	{
		if (i % j == 0)
			write(j + " ");
	}
	print()
}
```


I decided to use two for loops for this program. One to loop through numbers 1-100, and one to loop through each potential divisor. The two for loops would use variables i and j. For each dividend(i), it checks through each number(j) and prints it if it is a divisor of i.

The print statement at the end of the outer for loop is to skip a line. We wrote (j + " ") to add a space between each divisor.

<h3>Python, 80 bytes</h3>


```Python
for i in range(1,101):
	[print(j,end=' ')for j in range(1,101)if i%j==0];print()
```

<b>Ungolfed:</b>

```Python
for i in range(1, 101):
	for j in range(1,101):
		if i%j == 0:
			print(j, end=' ')
	print()
```


This Python program uses the same exact logic that the Javascript program uses.