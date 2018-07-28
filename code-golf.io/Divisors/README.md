<h1>Divisors</h1>
<b>Category:</b> Easy<br>
> A number is a divisor of another number if it can divide into it with no remainder.
> 
> Print the positive divisors of each number from 1 to 100 inclusive, on their own line, with each divisor separated by a space.

<h2>Write-up</h2>

<h3>Javascript</h3>

```
for(let i=1;i<101;i++){for(let j=1;j<101;j++)if(i%j==0)write(j+" ");print()}
```