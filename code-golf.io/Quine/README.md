<h1>Quine</h1>
<b>Category:</b> Easy
<br><br>

> A quine is a non-empty computer program which takes no input and produces a copy of its own source code as its only output, produce such a program.

> Trailing whitespace is NOT stripped from the output for this hole.

<h3>Quine, 19 bytes</h3>


```Quine
echo $BASH_COMMAND
```

<b>Ungolfed:</b>

```Quine
echo $BASH_COMMAND
```

There is a <a href="https://stackoverflow.com/questions/40933213/shortest-non-null-bash-quine">Stack Overflow</a> that provides an immediate answer to the question.
