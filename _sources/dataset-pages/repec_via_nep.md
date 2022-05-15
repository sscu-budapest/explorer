# RePEc via NEP

```{include} ../homes/repec_via_nep.md
```

## ERD

```{mermaid}
erDiagram
  authorship {    
    VARCHAR paper__pid PK     
    VARCHAR author__aid PK 
  }
  paper {    
    VARCHAR link      
    FLOAT year      
    VARCHAR abstract      
    VARCHAR title      
    VARCHAR institution      
    VARCHAR pid PK 
  }
  nep {    
    VARCHAR title      
    VARCHAR info      
    VARCHAR nid PK 
  }
  nep_inclusion {    
    VARCHAR paper__pid FK     
    INTEGER ind PK     
    VARCHAR issue__neid PK 
  }
  nep_issue {    
    VARCHAR nep__nid FK     
    DATETIME published      
    VARCHAR neid PK 
  }
  authorship ||--|{ paper : "paper__pid -> pid"
  nep_inclusion ||--|{ nep_issue : "issue__neid -> neid"
  nep_inclusion ||--|{ paper : "paper__pid -> pid"
  nep_issue ||--|{ nep : "nep__nid -> nid"
```


## Exploration / Analysis



## Tables

> There are 5 tables and the [sources](#sources) are **checked for updates at 00:00 am, on day 1 of the month** 




:::::{panels} :column: col-12

::::{div} row

```{div} col-9
**Authorship Table**
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/authorship.csv">{badge}`Download CSV,badge-primary`</a>
```
::::

^^^
::::{div} row

```{div} col-4
**Size**: 759888 × 2 (24.03 MB)
```

```{div} col-5
**Last Changed**: 2022-05-14 23:45
```

```{div} col-3

 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/authorship-profile.html">{badge}`Open Table Profile,badge-success`</a>

```

::::

:::::




:::::{panels} :column: col-12

::::{div} row

```{div} col-9
**Nep Inclusion Table**
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_inclusion.csv">{badge}`Download CSV,badge-primary`</a>
```
::::

^^^
::::{div} row

```{div} col-4
**Size**: 1067753 × 3 (39.69 MB)
```

```{div} col-5
**Last Changed**: 2022-05-14 23:45
```

```{div} col-3

 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_inclusion-profile.html">{badge}`Open Table Profile,badge-success`</a>

```

::::

:::::




:::::{panels} :column: col-12

::::{div} row

```{div} col-9
**Nep Issue Table**
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_issue.csv">{badge}`Download CSV,badge-primary`</a>
```
::::

^^^
::::{div} row

```{div} col-4
**Size**: 81252 × 3 (2.94 MB)
```

```{div} col-5
**Last Changed**: 2022-05-14 23:45
```

```{div} col-3

 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_issue-profile.html">{badge}`Open Table Profile,badge-success`</a>

```

::::

:::::




:::::{panels} :column: col-12

::::{div} row

```{div} col-9
**Nep Table**
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep.csv">{badge}`Download CSV,badge-primary`</a>
```
::::

^^^
::::{div} row

```{div} col-4
**Size**: 97 × 3 (8.37 kB)
```

```{div} col-5
**Last Changed**: 2022-04-24 21:41
```

```{div} col-3

 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep-profile.html">{badge}`Open Table Profile,badge-success`</a>

```

::::

:::::




:::::{panels} :column: col-12

::::{div} row

```{div} col-9
**Paper Table**
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/paper.csv">{badge}`Download CSV,badge-primary`</a>
```
::::

^^^
::::{div} row

```{div} col-4
**Size**: 381196 × 6 (116.25 MB)
```

```{div} col-5
**Last Changed**: 2022-05-14 23:46
```

```{div} col-3

 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/paper-profile.html">{badge}`Open Table Profile,badge-success`</a>

```

::::

:::::




## Sources

- project url: https://github.com/sscu-budapest/articledata
- data downloaded from
  - https://econpapers.repec.org
  - http://nep.repec.org/
  - https://logec.repec.org

