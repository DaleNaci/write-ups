<h1>Pangram Grep</h1>
<b>Category:</b> Medium
<br><br>

> A pangram is a sentence that uses every letter of a given alphabet.

> Write a program that will receive various sentences as arguments and print those that are valid pangrams.

<h2>Write-up</h2>

<h3>Python, 79 bytes</h3>


```Python
import sys
[print(s)for s in sys.argv if{*map(chr,range(65,91))}<={*s.upper()}]
```

<b>Ungolfed:</b>

```Python
import sys
for s in sys.argv:
    if {*map(chr, range(65, 91))} <= {*s.upper()}:
        print(s)
```

This program takes advantage of set comparisons.

I start with `for s in sys.argv`, which loops through each argument. Note that this does loop through the argument that calls the Python script, but it does not cause any actual issues in the code, since it is not a pangram.

`{*CODE}` creates a set out of CODE, which ends up being less characters than what I initially had, `{set(CODE)}`. Our code is comparing the alphabet to a set of `s.upper()`, an uppercase version of the string argument. I chose uppercase because I can use 2 two-digit numbers for `range()`, instead of a two and three-digit number.

`map(chr,range(65,91))` creates the entire alphabet. `map()` takes two arguments. The first argument is a function, and the second argument is a list or set of some sort. The function is applied to every item inside the second argument. `chr()` converts numbers to ASCII values, and 65-91 is A-Z.

We are using `<=` to compare the two sets. We initially just had `==`, but the string arguments had punctuation, so using `<=` accounted for the errors.