as always, lets look at he size of the file
```bash
cat logs.txt | wc 
      0       1 1592268
```
thats weird aint it?

hmmmm, maybe there is sth written within it

```bash
head -c 10 logs.txt
iVBORw0KGg
```
maybe encrypted?

```bash
head -c 10 logs.txt  | base64 -d
PNG
```

hmmmm interesting 



```bash
cat logs.txt | base64 -d > exmaple.png
#-----------------------------------------------
file exmaple.png 
exmaple.png: PNG image data, 896 x 1152, 8-bit/color RGB, non-interlaced
```

we get a certain string in the picture:
```bash
7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E675F35636363376362307D
```
if we can be able to decipher this(from hex) in cyberchef we might get our lovely flag

```bash
picoCTF{forensics_analysis_is_amazing_5ccc7cb0}
```
