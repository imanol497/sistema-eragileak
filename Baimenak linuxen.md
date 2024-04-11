# Baimenak Linux
- [Baimenak Linux](#baimenak-linux)
  - [Fitxategi eta direktorioen baimenak](#fitxategi-eta-direktorioen-baimenak)
    - [Baimena taldeak](#baimena-taldeak)
    - [Baimenak esleitzen modu simbolikoan](#baimenak-esleitzen-modu-simbolikoan)
    - [Baimenak modu oktalea](#baimenak-modu-oktalea)
    - [Baimenak modu oktalea](#baimenak-modu-oktalea-1)
  - [Sticky bit baimena](#sticky-bit-baimena)

## Fitxategi eta direktorioen baimenak

Fitxategi eta direktorioen baimenak hurrengo aginduarekin ikusi ditzakegu

```bash
ls -a
```

### Baimena taldeak

- **Jabea(user)**: Fitxategi bat sortzen dugunean, sortzailea jabea izango da defektuz.
- **Talde(group)**: fitxategi baten jabetza talde bati ere bai dagokio.
- **Besteak(other)**: Jabeak edo taldeak ez direnak.

![
](Capture.PNG)

### Baimenak esleitzen modu simbolikoan

Adibidez, Jabeari (user) exekutatzeko baimena honela eman ahal diogu.

```Bash
chmod U+X froga.txt
```

### Baimenak modu oktalea

Honela taldeari eta besteei exekuzio eta idazteko baimenak emango dizkigu.
```Bash
chmod go+wx froga.txt
```

Besteei, irakurtzeko baimena horrela exekuzio eta idazteko baimena
```Bash
chmod o-r froga.txt
```

### Baimenak modu oktalea

- 0 = 000 = --- = Baimenik gabe
- 1 = 001 = --x = Exekutazio baimena
- 2 = 010 = -W- = Idazteko baimena
- 3 = 011 = -wx = Idazteko eta exekutatzeko
- 4 = 100 = r-- = Irakurtzeko baimena
- 5 = 101 = r-x = Irakurtzeko eta exekutatzeko baimena
- 6 = 110 = rw- = Irakurtzeko eta idazteko baimena
- 7 = 111 = rwx = baimena guztiak
  
Baimen guztiak kentzeko
```Bash
chmod 000 froga.txt
```
Baimen guztiak gehitzeko
```Bash
chmod 777 froga.txt
```
Exekutatzeko eta irakurtzeko baimena
```Bash
chmod 775 froga.txt
```

## Sticky bit baimena

Sticky bita daukat fitxategi edo direktorio bat bakarrik jabea edo root-ak aldatu ditzake izena edo ezabatu

Sticky bit gehitzeko
```Bash
chmod +t froga.txt
```




