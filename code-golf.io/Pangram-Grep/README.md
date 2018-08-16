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

[EXPLANATION]