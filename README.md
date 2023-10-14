# Human Readable Twemoji
[Twemoji](https://github.com/twitter/twemoji) but the filenames are converted from codepoints to be human readable and easily searchable.

---

I used `emoji` (PyPi) and `emoji.unicode_codes.EMOJI_DATA` with some additional handling. *Example:*
```py
  if char in '().!':
      name = name.replace(char, '')
  elif char == '#':
      name = name.replace(char, 'number_sign')
  else:
      name = name.replace(char, '_')

  numbers = {
      '1st': 'first',
      '2nd': 'second',
      '3rd': 'third',
```
 Not perfect, there are probably some funky names.
