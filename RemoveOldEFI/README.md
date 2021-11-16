# Warning, follow the steps very carefully, can make your system unbootable

## Boot Menu and old EFI entries

![oldefi](oldefi.png)

- Here ubuntu is the old efi system

## Steps to remove old EFI entries from Boot Menu

- Boot to Windows and in console type

```console
C:\> bcedit /enum firmware
```

[efi](efi.png)

- This is the result which shows all the efi entries in our system


