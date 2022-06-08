# Hungarian Elections

```{include} ../datasets/hungarian_elections/description.md
```

## Entity Relationship Diagram (ERD)

```{admonition} What is an Entity Relationship Diagram (ERD)?
:class: dropdown
An **entity relationship diagram (ERD)** shows the relationships of entity sets stored in a database. An entity in this context is an object, a component of data, for example a variable. An entity set is a collection of similar entities. These entities can have attributes that define their properties.

By defining the entities, and their attributes, and showing the relationships between them, an ER diagram illustrates the logical structure of databases. 

Each table demonstrates an entity set, where the rows represent the entities. Each entity set contains a **primary key (PK)** which is unique in the table. A primary key can be one entity, for example, a tax number or a set of entities like longitude and latitude in spatial data.

An entity set may have got a **foreign key (FK)**. It means that the table is connected to another table's primary key. This **relationship** can be represented by a line with a **sign** on its every ending. The sign specifies how many instances of an entity relate to one instance of another entity:
- double lines (one)
- branching line (more)
```


```{mermaid}
erDiagram
  affiliation {    
    VARCHAR organization FK     
    VARCHAR party  
  }
  nominating_organization {    
    VARCHAR nid PK 
  }
  district_hierarchy {    
    VARCHAR child FK     
    VARCHAR parent FK 
  }
  geographical_unit {    
    VARCHAR level_info      
    VARCHAR name      
    VARCHAR unit_id PK 
  }
  election {    
    BOOLEAN is_individual      
    DATETIME start_date      
    VARCHAR election_id PK 
  }
  election_precinct {    
    VARCHAR election_id FK     
    FLOAT eligible_voters      
    BOOLEAN external_votes      
    VARCHAR geo_info      
    VARCHAR geo_unit_id FK     
    VARCHAR name      
    VARCHAR precinct_id PK 
  }
  vote_record {    
    VARCHAR organization FK     
    VARCHAR precinct_id FK     
    INTEGER vote_count      
    VARCHAR vid PK 
  }
  affiliation ||--|{ nominating_organization : "organization -> nid"
  district_hierarchy ||--|{ geographical_unit : "parent -> unit_id; child -> unit_id"
  election_precinct ||--|{ geographical_unit : "geo_unit_id -> unit_id"
  election_precinct ||--|{ election : "election_id -> election_id"
  vote_record ||--|{ nominating_organization : "organization -> nid"
  vote_record ||--|{ election_precinct : "precinct_id -> precinct_id"
```


## Exploratory Data Analysis (EDA)

```{admonition} What does exploratory data analysis contain?
:class: dropdown
These are some summaries of the initial analyses we conducted on the tables of the dataset. They are based on our ideas that we think can be **further explored in a research project**.

The exploration notebooks can be checked by clicking on the {badge}`Open Notebook,badge-success` button. If you just want to see the output figures of the analysis, then open them with the {badge}`Figures,badge-success` button.
```




:::::{panels} 
    :body: bg-warning
    :column: col-12

::::{div} row

```{div} col-4
**Hungarian elections analysis**
```

```{div} col-5
 <a href="../datasets/hungarian_elections/intro.html">{badge}`Open Notebook,badge-success`</a>
```


    
    



```{div} col-3
<button class="sphinx-bs badge badge-success" onclick="hideReveal('slideshow', 0, true)" >Figures</button>

```
::::
:::::

::::::{div} slideshow start-dis
:::::{panels}
:container: container-lg
:column: col-12

::::{div} row 




:::{div} myslides start-dis col-12 slide-container
```{include} ../datasets/hungarian_elections/intro/assets/out-14.html
```
:::

:::{div} myslides start-dis col-12 slide-container
```{include} ../datasets/hungarian_elections/intro/assets/out-15.html
```
:::


::::

^^^
::::{div} row

<div class = "col-6 docutils" align = "right">
<button  onclick="slideImage(0, -1)">&#10094;</button>
</div>

<div class = "col-6 docutils" align = "left">
<button  onclick="slideImage(0, 1)">&#10095;</button>
</div>

::::

:::::
::::::


## Tables

```{admonition} How should I use this?
:class: dropdown

**Table information**

Each table has a Table Profile, generated by [pandas-profiling](https://github.com/ydataai/pandas-profiling). This includes descriptive statistics based on the table data and metadata, which can **save significant time during the pre-analysis**. Each profiling contains descriptives of the variables and additionally may show interactions, correlations, missing data information, and samples of the data. To see the profiling click on {badge}`Open Table Profile,badge-success`.

Furthermore, you can check the first 5 rows of the tables by clicking on the {badge}`First 5 rows,badge-success` button.

**Download links**

The table data can be downloaded in CSV format with {badge}`Download CSV,badge-primary` button. Before this step, we recommend checking the table profile!

**Updating information**

Some datasets are updated periodically. In this case, you can check the updating period at the top of this section.
```

> There are 7 tables




:::::{panels} :column: col-12

::::{div} row

```{div} col-4
**Affiliation Table**
```

```{div} col-5
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/affiliation.csv">{badge}`Download CSV,badge-primary`</a>
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/affiliation-profile.html">{badge}`Open Table Profile,badge-success`</a>
```

::::

^^^
::::{div} row

```{div} col-4
**Size**: 257 × 2 (6.92 kB)
```

```{div} col-5
**Last Changed**: 2022-06-07 15:18
```

```{div} col-3
<button class = "sphinx-bs badge badge-success" onclick="hideReveal('head-dataframe', 0)">First 5 rows</button>
```
::::
:::::

::::{div} head-dataframe start-dis col-12 slide-container
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>party</th>
      <th>organization</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>MSZDP</td>
      <td>MSZDP</td>
    </tr>
    <tr>
      <th>1</th>
      <td>MSZP</td>
      <td>MSZP</td>
    </tr>
    <tr>
      <th>2</th>
      <td>SZDSZ</td>
      <td>SZDSZ</td>
    </tr>
    <tr>
      <th>3</th>
      <td>FÜGGETLEN</td>
      <td>FÜGGETLEN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>MDF</td>
      <td>MDF</td>
    </tr>
  </tbody>
</table>
</div>
::::



:::::{panels} :column: col-12

::::{div} row

```{div} col-4
**Nominating Organization Table**
```

```{div} col-5
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/nominating_organization.csv">{badge}`Download CSV,badge-primary`</a>
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/nominating_organization-profile.html">{badge}`Open Table Profile,badge-success`</a>
```

::::

^^^
::::{div} row

```{div} col-4
**Size**: 219 × 1 (3.07 kB)
```

```{div} col-5
**Last Changed**: 2022-06-07 15:18
```

```{div} col-3
<button class = "sphinx-bs badge badge-success" onclick="hideReveal('head-dataframe', 1)">First 5 rows</button>
```
::::
:::::

::::{div} head-dataframe start-dis col-12 slide-container
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>nid</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>MSZDP</td>
    </tr>
    <tr>
      <th>1</th>
      <td>MSZP</td>
    </tr>
    <tr>
      <th>2</th>
      <td>SZDSZ</td>
    </tr>
    <tr>
      <th>3</th>
      <td>FÜGGETLEN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>MDF</td>
    </tr>
  </tbody>
</table>
</div>
::::



:::::{panels} :column: col-12

::::{div} row

```{div} col-4
**Election Table**
```

```{div} col-5
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/election.csv">{badge}`Download CSV,badge-primary`</a>
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/election-profile.html">{badge}`Open Table Profile,badge-success`</a>
```

::::

^^^
::::{div} row

```{div} col-4
**Size**: 28 × 3 (0.95 kB)
```

```{div} col-5
**Last Changed**: 2022-06-07 15:18
```

```{div} col-3
<button class = "sphinx-bs badge badge-success" onclick="hideReveal('head-dataframe', 2)">First 5 rows</button>
```
::::
:::::

::::{div} head-dataframe start-dis col-12 slide-container
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>election_id</th>
      <th>is_individual</th>
      <th>start_date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>hun-1990-indiv-1</td>
      <td>True</td>
      <td>1990-03-25</td>
    </tr>
    <tr>
      <th>1</th>
      <td>hun-1990-party-1</td>
      <td>False</td>
      <td>1990-03-25</td>
    </tr>
    <tr>
      <th>2</th>
      <td>hun-1990-indiv-2</td>
      <td>True</td>
      <td>1990-04-08</td>
    </tr>
    <tr>
      <th>3</th>
      <td>hun-1990-party-2</td>
      <td>False</td>
      <td>1990-04-08</td>
    </tr>
    <tr>
      <th>4</th>
      <td>hun-1994-indiv-1</td>
      <td>True</td>
      <td>1994-05-08</td>
    </tr>
  </tbody>
</table>
</div>
::::



:::::{panels} :column: col-12

::::{div} row

```{div} col-4
**District Hierarchy Table**
```

```{div} col-5
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/district_hierarchy.csv">{badge}`Download CSV,badge-primary`</a>
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/district_hierarchy-profile.html">{badge}`Open Table Profile,badge-success`</a>
```

::::

^^^
::::{div} row

```{div} col-4
**Size**: 3224 × 2 (125.95 kB)
```

```{div} col-5
**Last Changed**: 2022-06-07 15:18
```

```{div} col-3
<button class = "sphinx-bs badge badge-success" onclick="hideReveal('head-dataframe', 3)">First 5 rows</button>
```
::::
:::::

::::{div} head-dataframe start-dis col-12 slide-container
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>parent</th>
      <th>child</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>hun-region313509025f</td>
      <td>hun-main4f04c03969</td>
    </tr>
    <tr>
      <th>1</th>
      <td>hun-region313509025f</td>
      <td>hun-main7a10a1d71e</td>
    </tr>
    <tr>
      <th>2</th>
      <td>hun-region313509025f</td>
      <td>hun-maince30d532ee</td>
    </tr>
    <tr>
      <th>3</th>
      <td>hun-region313509025f</td>
      <td>hun-mainc6e666f370</td>
    </tr>
    <tr>
      <th>4</th>
      <td>hun-region313509025f</td>
      <td>hun-mainb399cbef78</td>
    </tr>
  </tbody>
</table>
</div>
::::



:::::{panels} :column: col-12

::::{div} row

```{div} col-4
**Geographical Unit Table**
```

```{div} col-5
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/geographical_unit.csv">{badge}`Download CSV,badge-primary`</a>
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/geographical_unit-profile.html">{badge}`Open Table Profile,badge-success`</a>
```

::::

^^^
::::{div} row

```{div} col-4
**Size**: 3229 × 3 (128.04 kB)
```

```{div} col-5
**Last Changed**: 2022-06-07 15:18
```

```{div} col-3
<button class = "sphinx-bs badge badge-success" onclick="hideReveal('head-dataframe', 4)">First 5 rows</button>
```
::::
:::::

::::{div} head-dataframe start-dis col-12 slide-container
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>unit_id</th>
      <th>name</th>
      <th>level_info</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>hun-region313509025f</td>
      <td>BUDAPEST</td>
      <td>settlement</td>
    </tr>
    <tr>
      <th>1</th>
      <td>hun-regionb1bd8046e2</td>
      <td>FEJÉR</td>
      <td>county</td>
    </tr>
    <tr>
      <th>2</th>
      <td>hun-regiond54715d396</td>
      <td>JÁSZ-NAGYKUN-SZOLNOK</td>
      <td>county</td>
    </tr>
    <tr>
      <th>3</th>
      <td>hun-region93e2b0688c</td>
      <td>BARANYA</td>
      <td>county</td>
    </tr>
    <tr>
      <th>4</th>
      <td>hun-regionfe72b78f8e</td>
      <td>HEVES</td>
      <td>county</td>
    </tr>
  </tbody>
</table>
</div>
::::



:::::{panels} :column: col-12

::::{div} row

```{div} col-4
**Election Precinct Table**
```

```{div} col-5
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/election_precinct.csv">{badge}`Download CSV,badge-primary`</a>
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/election_precinct-profile.html">{badge}`Open Table Profile,badge-success`</a>
```

::::

^^^
::::{div} row

```{div} col-4
**Size**: 272194 × 7 (25.87 MB)
```

```{div} col-5
**Last Changed**: 2022-06-07 15:18
```

```{div} col-3
<button class = "sphinx-bs badge badge-success" onclick="hideReveal('head-dataframe', 5)">First 5 rows</button>
```
::::
:::::

::::{div} head-dataframe start-dis col-12 slide-container
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>precinct_id</th>
      <th>name</th>
      <th>geo_info</th>
      <th>eligible_voters</th>
      <th>external_votes</th>
      <th>geo_unit_id</th>
      <th>election_id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1031</td>
      <td>BUDAPEST I-001</td>
      <td>BUDAPEST          01</td>
      <td>806.0</td>
      <td>False</td>
      <td>hun-main4f04c03969</td>
      <td>hun-1990-indiv-1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>137128</td>
      <td>BUDAPEST I-001</td>
      <td>BUDAPEST          01</td>
      <td>811.0</td>
      <td>False</td>
      <td>hun-main4f04c03969</td>
      <td>hun-1990-party-1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1032</td>
      <td>BUDAPEST I-002</td>
      <td>BUDAPEST          01</td>
      <td>814.0</td>
      <td>False</td>
      <td>hun-main4f04c03969</td>
      <td>hun-1990-indiv-1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>137129</td>
      <td>BUDAPEST I-002</td>
      <td>BUDAPEST          01</td>
      <td>820.0</td>
      <td>False</td>
      <td>hun-main4f04c03969</td>
      <td>hun-1990-party-1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1033</td>
      <td>BUDAPEST I-003</td>
      <td>BUDAPEST          01</td>
      <td>632.0</td>
      <td>False</td>
      <td>hun-main4f04c03969</td>
      <td>hun-1990-indiv-1</td>
    </tr>
  </tbody>
</table>
</div>
::::



:::::{panels} :column: col-12

::::{div} row

```{div} col-4
**Vote Record Table**
```

```{div} col-5
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/vote_record.csv">{badge}`Download CSV,badge-primary`</a>
```

```{div} col-3
 <a href="https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/vote_record-profile.html">{badge}`Open Table Profile,badge-success`</a>
```

::::

^^^
::::{div} row

```{div} col-4
**Size**: 1996280 × 4 (49.57 MB)
```

```{div} col-5
**Last Changed**: 2022-06-07 15:19
```

```{div} col-3
<button class = "sphinx-bs badge badge-success" onclick="hideReveal('head-dataframe', 6)">First 5 rows</button>
```
::::
:::::

::::{div} head-dataframe start-dis col-12 slide-container
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>variable</th>
      <th>vid</th>
      <th>vote_count</th>
      <th>organization</th>
      <th>precinct_id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>19</td>
      <td>MSZDP</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>45</td>
      <td>MSZP</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>163</td>
      <td>SZDSZ</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>28</td>
      <td>FÜGGETLEN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>201</td>
      <td>MDF</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>
::::


## Sources

- project url: https://github.com/sscu-budapest/electiondata
- data downloaded from
  - https://valtor.valasztas.hu
  - https://valtor.valasztas.hu/valtort/jsp/tmd1.jsp?TIP=2

