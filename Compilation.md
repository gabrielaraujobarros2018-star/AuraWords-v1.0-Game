# AuraWords - Compiling

## Compilation -> img

Example build pipeline:

```
g++ *.cpp -O2 -static -o AuraWords.img
```

then move:

```
mv AuraWords.img \
/palisade/os/framework/framework.Apps/programIMPORTS.Custom/adminApps/
```