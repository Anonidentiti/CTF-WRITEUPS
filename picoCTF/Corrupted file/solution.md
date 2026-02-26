So we are presented with a corrupted file<br>
We need to know what the problem is it.<br>

so i ran <br>
```bash
binwalk file

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------

```

You get nothing <br>

so i need to know what is the first 5 strings i can get and see what i have<br>

```bash
strings file | head -n 5

JFIF
 $.' ",#
(7),01444
'9=82<.342
!22222222222222222222222222222222222222222222222222
```

The JFIF does say sth about this file<br>
when check out what JFIF is, you find out that a JFIF (JPEG File Interchange Format)<br> is a image standard that will later be used as jpg or jpeg <br>
what does that say? <br>

we need to know the hex used and see if it follows the official image formats needed


we can use <br>
```link
https://en.wikipedia.org/wiki/List_of_file_signatures
```

we can see here that the hex code of jfif is <br>

```bash
FF D8 FF E0 00 10 4A 46 49 46 00 01
``` 
that says sth about this. if the first two bytes dont follow that rule then you can change where necessary <br>

In this case we have: <br>

```bash
5C 78 FF E0  00 10 4A 46  49 46 00 01
```

see the first two bytes of the hex ?

we have to change it and use the template posted earlier
