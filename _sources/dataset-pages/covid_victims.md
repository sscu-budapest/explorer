# Covid Victims

```{include} ../homes/covid_victims.md
```

## ERD

```{mermaid}
erDiagram
  covid_victim {    
    INTEGER age      
    DATETIME estimated_date      
    BOOLEAN is_male      
    VARCHAR raw_conditions      
    BOOLEAN condition__lungs      
    BOOLEAN condition__heart      
    BOOLEAN condition__blood_pressure      
    BOOLEAN condition__diabetes      
    BOOLEAN condition__obesity      
    FLOAT positive_rate      
    INTEGER total_vaccinations      
    INTEGER people_vaccinated      
    INTEGER people_fully_vaccinated      
    INTEGER total_boosters      
    INTEGER serial PK 
  }
```


## Exploration / Analysis



## Tables

> There is 1 table and the [sources](#sources) are **checked for updates at 04:00 pm** 




:::::{panels} :column: col-12

::::{div} row

```{div} col-9
**Covid Victim Table**
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/covid_victims/covid_victim.csv">{badge}`Download CSV,badge-primary`</a>
```
::::

^^^
::::{div} row

```{div} col-4
**Size**: 46266 × 15 (6.14 MB)
```

```{div} col-5
**Last Changed**: 2022-05-17 15:21
```

```{div} col-3

 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/covid_victims/covid_victim-profile.html">{badge}`Open Table Profile,badge-success`</a>

```

::::

:::::




## Sources

- project url: https://github.com/sscu-budapest/dabble
- data downloaded from
  - https://koronavirus.gov.hu/elhunytak
  - https://covid.ourworldindata.org
  - https://www.worldometers.info/coronavirus/country/hungary/

