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

And run

```
emerge app-misc/lcdproc
```
