<h1>Christmas Trees</h1>
<b>Category:</b> Medium
<br><br>

> Print a size ascending range of Christmas trees using asterisks, ranging from size 3 to size 9, each tree separated by a blank line.

A size 3 tree should look like this, with a single centered asterisk for the trunk:

```
   *
  ***
 *****
   *
```

With the largest size 9 tree looking like this:

```
         *
        ***
       *****
      *******
     *********
    ***********
   *************
  ***************
 *****************
         *
```

<h2>Write-up</h2>

<h3>Python, 92 bytes</h3>


```Python
for i in range(3,10):
    for j in range(i):print(' '*(i-j)+'*'*(j*2+1))
    print(' '*i+'*'+'\n')
```

<b>Ungolfed:</b>

```Python
for i in range(3, 10):
    for j in range(i):
        print(' ' * (i - j) + '*' * (j * 2 + 1))
    print(' ' * i + '*' + '\n')
```


A decent amount of math/logic goes into this. It starts with a for loop that goes from 3-9, because for each Christmas Tree there are those number of rows (besides the bottom row).

We print the spaces that go from i to 1, so we print `' ' * (i - j)`. The number of asterisks also go up in two's from 1 asterisk, so we use `(j * 2 + 1)`. `j` starts at 0 and is multiplied be 2, so it will go up in multiples of two. We also have a + 1 so that it will started 1 unit higher.

At the end of the outer for loop, we add a group of spaces followed by a single asterisk.