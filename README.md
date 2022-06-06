# Netsuite Code Snippets - By Shayan Shaikh

The essential collection of Netsuite Code Snippets and commands.

![snippets-in-action](https://user-images.githubusercontent.com/42208796/169110960-207fe300-f61e-4b78-a0fd-c53752ce00b5.gif)


## Snippets

| Snippet               | Renders                                       | Version   |
| -------------------   | --------------------------------------------- | --------- |
| `ns-fun`              | NS Simple Function                            | V1        |
| `ns-class`            | NS Class Function                             | V1        |
| `ns-arrow-fun`        | NS Arrow Function                             | V1        |
| `ns-udb`              | NS Utility Debug                              | V1        |
| `ns-ua`               | NS Utility Audit                              | V1        |
| `ns-ue`               | NS Utility Emergency                          | V1        |
| `ns-ute`              | NS Utility Throw Exception                    | V1        |
| `ns-uex`              | NS Utility Exception                          | V1        |
| `ns-extend-cc`        | Extend Connector Common script                | V1        |
| `ns-extend-fcf`       | Extend Client Factory script                  | V1        |
| `ns-extend-iel`       | Extend Item Export script                     | V1        |
| `ns-script-ue`        | NS Userevent Script                           | V1        |
| `ns-copy-lib`         | Copy Script Libraries                         | V1        |
| `ns-search-rec`       | Function To Search The Record Existance       | V1        |
| `ns-upsert-rec`       | NS Create/Load Record                         | V1        |
| `ns-fun-v2`           | NS Simple Function                            | V2        |
| `ns-class-v2`         | NS Class Function                             | V2        |
| `ns-arrow-fun-v2`     | NS Arrow Function                             | V2        |
| `ns-udb-v2`           | NS Utility Debug                              | V2        |
| `ns-ua-v2`            | NS Utility Audit                              | V2        |
| `ns-ue-v2`            | NS Utility Emergency                          | V2        |
| `ns-ute-v2`           | NS Utility Throw Exception                    | V2        |
| `ns-uex-v2`           | NS Utility Exception                          | V2        |
| `ns-load-so-v2`       | Load and Submit Record                        | V2        |
| `ns-trans-so-v2`      | Transform Record                              | V2        |

## Full Expansions

### ns-arrow-fun | NS Arrow Function

```javascript
/**
* @description 
*/
const | = () => { 
    const logTitle = 'TM_FILENAME => |'; 
    try { 
        Utility.logDebug(logTitle, 'START'); 
 
 
        Utility.logDebug(logTitle, 'END');
    } catch (e) { 
        Utility.logException(logTitle, e); 
    }
}
```

### ns-fun  | NS Class Function

```javascript
| () { 
    const logTitle = 'TM_FILENAME => |'; 
    try { 
        Utility.logDebug(logTitle, 'START'); 
 
 
        Utility.logDebug(logTitle, 'END');
    } catch (e) { 
        Utility.logException(logTitle, e); 
    }
}
```


### ns-fun  | NS Simple Function

```javascript
function | () { 
    const logTitle = 'TM_FILENAME => |'; 
    try { 
        Utility.logDebug(logTitle, 'START'); 
 
 
        Utility.logDebug(logTitle, 'END');
    } catch (e) { 
        Utility.logException(logTitle, e); 
    }
}
```

### ns-copy-lib | Copy Script Libraries

```javascript
let fileForDependencies = nlapiLoadRecord("scheduledscript", 'ORIGIN_SCRIPT_ID');
let myScript = nlapiLoadRecord("scheduledscript", 'YOUR_SCRIPT_ID');
let librariesCount = fileForDependencies.getLineItemCount("libraries");
for (let i = 0; i < librariesCount; i++) {
    let scriptfile = fileForDependencies.getLineItemValue('libraries', 'scriptfile', i + 1);
    myScript.setLineItemValue('libraries', 'scriptfile', i + 1, scriptfile);
}
nlapiSubmitRecord(myScript);
```

<!-- herer -->
### ns-search-rec | Function To Search The Record Existance

```javascript
/**
* @param {} el
* @description 
*/
const isRecordExist = (el) => {
  const logTitle = 'TM_FILENAME => isRecordExist';
  try {
    const recordSearch = nlapiSearchRecord(
      'RECORD_ID',
      null,
      [['FIELD_ID', 'is', el]],
      [new nlobjSearchColumn('internalid').setSort(false)]
    );
    Utility.logDebug(logTitle, JSON.stringify({ recordSearch }));
    return recordSearch ? recordSearch[0].getValue('internalid') : false;
  } catch (e) {
    Utility.logException(logTitle, e);
  }
}
```

### ns-upsert-rec | NS Create/Load Record

```javascript
/**
* @param {} recordId
* @description 
*/
const upsertRecord = (recordId) => {
  const logTitle = 'TM_FILENAME => upsertF3ImageRecordData';
  try {
    const rec = recordId ? nlapiLoadRecord('RECORD_ID', recordId) : nlapiCreateRecord('RECORD_ID');
    rec.setFieldValue('FIELD_NAME', 'VALUE');
    return nlapiSubmitRecord(rec, true);
  } catch (e) {
    Utility.logException(logTitle, e);
  }
};
```

### ns-arrow-fun-v2 | NS Arrow Function

```javascript
/**
* @description 
*/
const | = () => { 
    const logTitle = 'TM_FILENAME => |'; 
    try { 
        utility.logDebug({ title: logTitle, details: 'START' }); 
 
 
        utility.logDebug({ title: logTitle, details: 'END' });
    } catch (e) { 
        utility.logException({ title: logTitle, details: e });
    }
}
```

### ns-fun-v2  | NS Class Function

```javascript
| () { 
    const logTitle = 'TM_FILENAME => |'; 
    try { 
        utility.logDebug({ title: logTitle, details: 'START' }); 
 
 
        utility.logDebug({ title: logTitle, details: 'END' });
    } catch (e) { 
        utility.logException({ title: logTitle, details: e });
    }
}
```


### ns-fun-v2  | NS Simple Function

```javascript
function | () { 
    const logTitle = 'TM_FILENAME => |'; 
    try { 
        utility.logDebug({ title: logTitle, details: 'START' }); 
 
 
        utility.logDebug({ title: logTitle, details: 'END' });
    } catch (e) { 
        utility.logException({ title: logTitle, details: e });
    }
}
```

### ns-udb | NS Utility Debug

```javascript
Utility.logDebug(logTitle, JSON.stringify({ | }));
```

### ns-ua | NS Utility Audit

```javascript
Utility.logAudit(logTitle, JSON.stringify({ | }));
```

### ns-ue | NS Utility Emergency

```javascript
Utility.logEmergency(logTitle, JSON.stringify({ | }));
```

### ns-ute | NS Utility Throw Exception

```javascript
Utility.throwException(logTitle, JSON.stringify({ | }));
```

### ns-uex | NS Utility Exception

```javascript
Utility.logException(logTitle, JSON.stringify({ | }));
```

### ns-udb-v2 | NS Utility Debug

```javascript
utility.logDebug({ title: logTitle, details: JSON.stringify({ | })});
```

### ns-ua-v2 | NS utility Audit

```javascript
utility.logAudit({ title: logTitle, details: JSON.stringify({ | })});
```

### ns-ue-v2 | NS utility Emergency

```javascript
utility.logEmergency({ title: logTitle, details: JSON.stringify({ | })});
```

### ns-ute-v2 | NS utility Throw Exception

```javascript
utility.throwException({ title: logTitle, details: JSON.stringify({ | })});
```

### ns-uex-v2 | NS utility Exception

```javascript
utility.logException({ title: logTitle, details: JSON.stringify({ | })});
```

### ns-get-value-v2 | NS Get Value V2

```javascript
|.getValue({ fieldId: '|' });
```

### ns-set-value-v2 | NS Set Value V2

```javascript
|.setValue({ fieldId: '|', value: | });
```

### ns-get-sublistvalue-v2 | NS Set Sublist Value V2

```javascript
|.getSublistValue({ sublistId: '|', fieldId: '|', line: | });
```

### ns-set-subvalue-v2 | NS Get Sublist Value V2

```javascript
|.setSublistValue({ sublistId: '|', fieldId: '|', line: |, value: | });
```

### ns-load-so-v2 | NS Load Sales Order V2

```javascript
const | = |.load({
  type: 'salesorder',
  id: |
});

|.setValue({ fieldId: '|', value: | });

const |Id = |.save({
  enableSourcing: false,
  ignoreMandatoryFields: true
});
```

### ns-trans-so-v2 | Transform Sales Order V2

```javascript
const | = |.transform({
  fromType: 'salesorder',
  fromId: |,
  toType: '|'
});

|.setValue({ fieldId: '|', value: | });

const |Id = |.save({
  enableSourcing: true,
  ignoreMandatoryFields: true
});
```


## Thank You! ❤️

Author Email: shayanshaikh996@gmail.com

© 2022 Shayan Shaikh.

