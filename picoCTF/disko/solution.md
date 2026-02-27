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

we Furthur on use fls to recover what files was used <br>
```bash
fls -r disko-1.dd
d/d 4:  bin
+ r/r 22:       sqlitebrowser
+ r/r 26:       x86_64-linux-gnu-python3.11-config
+ r/r 28:       dbus-daemon
+ r/r 31:       dbus-run-session
+ r/r 34:       dbus-cleanup-sockets
+ r/r 220660:   dbus-monitor
+ r/r 220662:   dbus-send
+ r/r 220666:   dbus-update-activation-environment
+ r/r 220668:   dbus-uuidgen
+ r/r 220671:   ncurses6-config
+ r/r 220674:   ncursesw6-config
+ r/r 224100:   setxkbmap
+ r/r 224102:   xkbbell
+ r/r 224104:   xkbcomp
+ r/r 224106:   xkbevd
+ r/r 224108:   xkbprint
+ r/r 224110:   xkbvleds
+ r/r 224112:   xkbwatch
+ r/r 224114:   cabextract
+ r/r 239588:   appres
+ r/r 239590:   editres
                 ...
+ r/r 1612633:  dpkg-divert
+ r/r 1612636:  dpkg-maintscript-helper
+ r/r 1612638:  dpkg-query
+ r/r 1612640:  dpkg-realpath
+ r/r 1612642:  dpkg-split
+ r/r 1612645:  dpkg-statoverride
+ r/r 1612647:  dpkg-trigger
+ r/r 1612650:  update-alternatives
+ r/r 1612652:  evil-winrm
+ r/r 1612654:  pydoc2.7
+ r/r 1612656:  pygettext2.7
+ r/r 1612658:  cvtsudoers
v/v 1612675:    $MBR
v/v 1612676:    $FAT1
v/v 1612677:    $FAT2
V/V 1612678:    $OrphanFiles
```
what a big file
