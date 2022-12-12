# GLK12232-25-SM-lcdproc
Matrix Orbital LCD GLK12232-25-SM with patches for lcdproc on Infoblox-1050-A.

Русская кириллица ASCII Windows 1251.

#### Upload font and bitmap to display:

```
Use https://www.matrixorbital.com/graphic-software
```

#### Build lcdproc on Gentoo:

Put patches to directory /etc/portage/app-misc/lcdproc/

Add to /etc/portage/package.use

```
app-misc/lcdproc menu
```

Add to /etc/portage/make.conf

```
lcd_devices="glk"
```

Set RS232 port (in BIOS) and LCD display speed to 115200 baud (More information in GLK12232-25-SM User Manual)
```
echo -n -e "\xfe\x39\x8A" > /dev/ttyS1

Speed Value (last byte)
20 Hex 9600 baud
0F Hex 19200 baud
95 Hex 57600 baud
03 Hex 76800 baud
8A Hex 115000 baud
```

And run

```
emerge app-misc/lcdproc
```
