# Baimenak Linux
- [Baimenak Linux](#baimenak-linux)
  - [Fitxategi eta direktorioen baimenak](#fitxategi-eta-direktorioen-baimenak)
    - [Baimena taldeak](#baimena-taldeak)
    - [Baimenak esleitzen modu simbolikoan](#baimenak-esleitzen-modu-simbolikoan)
    - [Baimenak modu oktalea](#baimenak-modu-oktalea)
    - [Baimenak modu oktalea](#baimenak-modu-oktalea-1)
  - [Sticky bit baimena](#sticky-bit-baimena)
  - [SUID eta GUID baimenak](#suid-eta-guid-baimenak)
    - [SUID](#suid)
  - [Ezaugarri bereziak - lsattr eta chattr](#ezaugarri-bereziak---lsattr-eta-chattr)
  - [Ariketak](#ariketak)
- [Ariketak](#ariketak-1)

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

## SUID eta GUID baimenak

### SUID

SUID aktibatuta dagoenean fitxategi hau exekutatzen duen erabiltzaileak sortazailearen baimenak izango ditu.

```bash
chmod u+s froga.txt
```

Sortu exekutable bat hurrengo edukiarekin

suidfroga.sh
```bash
#!/bin/bash
echo erabiltzailea
 id
 echo SUID
```

Ezarri SUID suidfroga.sh fitxategiari

```Bash
chmod u+s suidfroga.sh
```

```Bash
chmod 4755 suidfroga.sh
```

## Ezaugarri bereziak - lsattr eta chattr

Ezaugarri bereziak ikusteko `lsattr` agindua erabiliko dugu.

Ezaugarri bereziak aldatzeko `chattr` aginduak erabiliko dugu.

Adibidez, i atributoarekin fitxategi bat inmutablea bilakatzen dugu. Hau esan nahi du inork ezin duela aldatu ez ezabatu, ezta root-ek. Ezabatu nahi izaterakoan, i atributoa kendu beharko genioke lehenago.

```bash
chattr +i froga.txt
lsattr froga.txt
```

**u** ezaugarriarekin fitxategi bat ezabatzen dugunean, datuak gordeta gelditzen dira eta bere berreskurapena ahalbidetzen du.

```Bash
chattr +u froga.txt
```

**e** ezaugarriarekin fitxategi bat ezabatzen denean, okupatzen duen memoria zeroekin berridazten da.

```Bash
chattr +e froga.txt
```

**c** ezaugarriarekin fitxategi bat komprimituta gordeko da.
```Bash
chattr +c froga.txt
```

**a** ezaugarriarekin fitxategi bati bakarrik gehitu ahal zaizkio gauzak, hau da, ezin da aldatu aurretik zegoen ezer.
```Bash
chattr +a froga.txt
```

## Ariketak

# Ariketak

Lotu dagokion baimenarekin

- 462
- 123
- 711
- 333
- 161
- 765
- 567
- 101
- 162

- rwx--x--x
- --x-w--wx
- --x-----x
- -wx-wx-wx
- r-xrw-rxw
- rwxrw-
- --xrw--w-r
- r-rw-w-x







