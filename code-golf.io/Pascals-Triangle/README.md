<h1>Evil Numbers</h1>
<b>Category:</b> Easy
<br><br>

> Print the first 20 rows of Pascal's triangle.

<h3>Perl 6, 93 bytes</h3>


```Perl
for ^20 -> $i {for ^($i+1) -> $j {print(([*] 1..$i)/(([*] 1..$j)*([*] 1..$i-$j))," ")};say()}
```

<b>Ungolfed:</b>

```Perl
for ^20 -> $i
{
	for ^($i + 1) -> $j
	{
		print(([*] 1..$i) / (([*] 1..$j) * ([*] 1..$i-$j)), " ")
	};
	say()
}
```


This solution uses a factorial-based math formula to print out Pascal's Triangle: `(i!) / (j! * (i - j)!)`. In this formula, `i` is the row, and `j` is how far across each row the program is. For this program, I used nested for loops. The outer one loops through each row, and the inner loop points to the place in each row. I loop through each row `$i+1` times, because for each row there is an extra number, and the outer for loop also increments by 1, but since `$i` starts at 0, I add 1 to it.

The final `say()` is used to skip a line.