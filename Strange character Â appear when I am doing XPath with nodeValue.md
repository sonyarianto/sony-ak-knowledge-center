It's not about XPath at all but it's all about the document output.

The non-breaking space character when interpreted by DOM is a multibyte character and your script is trying to display only single-byte characters.

How to fix it?

Just use `utf8_decode()` function and everything will be OK.
