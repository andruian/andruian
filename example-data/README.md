# Andruian example data

This folder contains some testing data that can be used to get the sense of the framework functionality.

## Dataset
The data definitions below work over the same datasets, provided in folder [datasets](datasets).

The folder contains a [SPARQL CONSTRUCT query template](datasets/construct-query.sparql) which was used to construct the 
datasets and may be easily customized. The `CONSTRUCT` section of the query also shows the data structure. This query
is to be executed on the RÚIAN SPARQL endpoint here: https://ruian.linked.opendata.cz/sparql 

In short, three types of objects are created for each matching RÚIAN object. The source object links to the first
"transient", which links to the second "transient", which links to a RÚIAN object. See the diagram below:
```
<http://example.org/SourceObjectA>
              |
              |
      <http://a.property>
              |
              |
              v 
<http://example.org/FirstObject>
              |
              |
      <http://a.property>
              |
              |
              v
<http://example.org/SecondObject>
              |
              |
      <http://link.to.ruian>
              |
              |
              v
<http://some-ruian-object>
``` 

The data covers Prague and links to address places (`ruian:AdresníMísto`). The places are categorized based on the 
first letter of the street they are in.

## Data definitions
There are several folders with data definitions based on the implementation stage in which they were worked at.

#### localhost
Located in folder [localhost](localhost).

Used when working locally. The index server must be accessible on `http://localhost:8080`. 
The data definition defines an index server at URL `http://10.0.2.2:8080`. This URL corresponds to the localhost 
when used in an Android application running in an emulator.

#### Pointing to a testing Andruian instance
Located in folder [andruian-melkamar-cz](andruian-melkamar-cz).

This set of data definitions work with the demo instance of the Indexer component accessible at 
`http://andruian.melkamar.cz`. The definitions are ready-to-use as they are and may be linked to by 
using the Raw link.

Most of the definitions use the index server, 
[except for one](andruian-melkamar-cz/streets-starting-with-a-datadef-no-idx.ttl).
This definition does not specify an index server and is used to benchmark the framework when no geospatial 
indexing is done. It uses the smallest dataset, because even then it is fairly slow.