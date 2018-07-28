<h1>Evil Numbers</h1>
<b>Category:</b> Easy
<br><br>

> An evil number is a non-negative number that has an even number of 1s in its binary expansion.

> Print all the evil numbers from 0 to 50 inclusive, each on their own line.

> Numbers that are not evil are called odious numbers.

<h2>Write-up</h2>

<h3>Python, 58 bytes</h3>


```python
[print(i)for i in range(49)if str(bin(i)).count('1')%2==0]
```

This program only requires a single for loop to go through the numbers 0-48 (49 and 50 or not Evil Numbers).

Let's take a closer look at ```str(bin(i)).count('1')```. First, I convert i to a binary number. I want to use the .count() method to count the number of 1's, but .count() only works on strings. Thus, I add a str() method on bin(i) to convert it to a string. We then use ```%2==0``` check if the binary number has an even number of 1's.

<b>Ungolfed:</b>

```python
for i in range(49):
	if str(bin(i)).count('1') % 2 == 0:
		print(i)
```
