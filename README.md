# GLK12232-25-SM-lcdproc
Matrix Orbital LCD GLK12232-25-SM with patches for lcdproc on Infoblox-1050-A.

Русская кириллица ASCII Windows 1251.

#### Upload font and bitmap to display:

```
Use https://www.matrixorbital.com/graphic-software
```

#### Build lcdproc on Gentoo:

Put patches to directory /etc/portage/app-misc/lcdproc/

Put init script lcddvc to directory /etc/init.d/

Add to /etc/portage/package.use

```
app-misc/lcdproc menu
```

Add to /etc/portage/make.conf

```
lcd_devices="glk"
```

Set RS232 port (in BIOS) and LCD display speed to 115200 baud (More information in GLK12232-25-SM User Manual 8.1.12)
```
LCD display speed (254 57 [speed])
dec 254 - hex FE
dec 57 - hex 39

Speed Value (last byte)
20 Hex 9600 baud
0F Hex 19200 baud
95 Hex 57600 baud
03 Hex 76800 baud
8A Hex 115000 baud

echo -n -e "\xFE\x39\x8A" > /dev/ttyS1
```

And run

```
emerge app-misc/lcdproc
```

```
rc-service LCDd start
rc-service lcdproc start
```
