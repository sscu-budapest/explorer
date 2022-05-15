# Scimago Journals

```{include} ../homes/scimago_journals.md
```

## ERD

```{mermaid}
erDiagram
  journal {    
    INTEGER rank      
    FLOAT journal_rating      
    VARCHAR title      
    VARCHAR type      
    VARCHAR issn      
    INTEGER h_index      
    INTEGER total_docs_2021      
    FLOAT ref_per_doc      
    VARCHAR sjr_best_quartile      
    INTEGER total_docs_3years      
    INTEGER total_refs      
    INTEGER total_cites_3years      
    INTEGER citable_docs_3years      
    VARCHAR country      
    VARCHAR region      
    VARCHAR publisher      
    VARCHAR coverage      
    VARCHAR categories      
    INTEGER sourceid PK 
  }
```


## Exploration / Analysis



## Tables

> There is 1 table




:::::{panels} :column: col-12

::::{div} row

```{div} col-9
**Journal Table**
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/scimago_journals/journal.csv">{badge}`Download CSV,badge-primary`</a>
```
::::

^^^
::::{div} row

```{div} col-4
**Size**: 34664 × 20 (8.45 MB)
```

```{div} col-5
**Last Changed**: 2022-05-14 23:44
```

```{div} col-3

 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/scimago_journals/journal-profile.html">{badge}`Open Table Profile,badge-success`</a>

```

::::

:::::




## Sources

- project url: https://github.com/sscu-budapest/dabble
