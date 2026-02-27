as always, binwalk to a file investigation look up:<br>

```bash
binwalk disko-1.dd.gz 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             gzip compressed data, has original file name: "disko-1.dd", from Unix, last modified: 2025-05-15 18:48:28
1912348       0x1D2E1C        Zlib compressed data, default compression
1969133       0x1E0BED        Zlib compressed data, default compression
2348983       0x23D7B7        Zlib compressed data, default compression
2687663       0x2902AF        Zlib compressed data, default compression
2760400       0x2A1ED0        Zlib compressed data, default compression
2850250       0x2B7DCA        Zlib compressed data, default compression
2897644       0x2C36EC        Zlib compressed data, default compression
```

unzipping comes to mind.<br>
```bash
7z x disko-1.dd.gz
```
specifically we use 7z for extracting files with the gz extension <br>

