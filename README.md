# Folio3 Connector Snippets - By Shayan Shaikh

The essential collection of Folio3 Connector Snippets and commands.

![snippets-in-action](https://user-images.githubusercontent.com/42208796/169110960-207fe300-f61e-4b78-a0fd-c53752ce00b5.gif)


## Snippets

| Snippet               | Renders                                       |
| -------------------   | --------------------------------------------- |
| `ns-fun`              | NS Simple Function                            |
| `ns-class`            | NS Class Function                             |
| `ns-arrow-fun`        | NS Arrow Function                             |
| `ns-udb`              | NS Utility Debug                              |
| `ns-ua`               | NS Utility Audit                              |
| `ns-ue`               | NS Utility Emergency                          |
| `ns-ute`              | NS Utility Throw Exception                    |
| `ns-uex`              | NS Utility Exception                          |
| `ns-extend-cc`        | Extend Connector Common script  V1            |
| `ns-extend-fcf`       | Extend Client Factory script V1               |
| `ns-extend-iel`       | Extend Item Export script V1                  |
| `ns-script-ue`        | NS Userevent Script V1                        |

## Full Expansions

### f3-arrow-fun | F3 Arrow Function

```javascript
/**
* @description 
*/
const | = () => { 
    const logTitle = 'Untitled-1 => |'; 
    try { 
        Utility.logDebug(logTitle, 'START'); 
 
 
        Utility.logDebug(logTitle, 'END');
    } catch (e) { 
        Utility.logException(logTitle, e); 
    }
}
```

### f3-fun  | F3 Class Function

```javascript
| () { 
    const logTitle = 'Untitled-1 => |'; 
    try { 
        Utility.logDebug(logTitle, 'START'); 
 
 
        Utility.logDebug(logTitle, 'END');
    } catch (e) { 
        Utility.logException(logTitle, e); 
    }
}
```


### f3-fun  | F3 Simple Function

```javascript
function | () { 
    const logTitle = 'Untitled-1 => |'; 
    try { 
        Utility.logDebug(logTitle, 'START'); 
 
 
        Utility.logDebug(logTitle, 'END');
    } catch (e) { 
        Utility.logException(logTitle, e); 
    }
}
```


### udb | F3 Utility Debug

```javascript
Utility.logDebug(logTitle, JSON.stringify({ | }));
```

### ua | F3 Utility Audit

```javascript
Utility.logAudit(logTitle, JSON.stringify({ | }));
```

### ue | F3 Utility Emergency

```javascript
Utility.logEmergency(logTitle, JSON.stringify({ | }));
```

### ute | F3 Utility Throw Exception

```javascript
Utility.throwException(logTitle, JSON.stringify({ | }));
```

### uex | F3 Utility Exception

```javascript
Utility.logException(logTitle, JSON.stringify({ | }));
```

## Thank You! ❤️

Author Contact: shayanshaikh996@gmail.com

© 2022 Shayan Shaikh.

