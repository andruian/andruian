# RUIAN sample data

### `ruian-links.ttl`

RDF data defining some testing objects and linking them to RUIAN:

`ex:linkedobject-###### a ex:MyObject`
    - `ex:id`       contains the same number as url
    - `ex:someLink` links to sublinkObjects (below)
    
`ex:sublinkObject-#####`
    - `ex:linksTo`  links to RUIAN object of type AdresniMisto, 
      [example resource](http://ruian.linked.opendata.cz/resource/adresni-mista/72715057) 

### `ruian-datadef.ttl`

Andruian DataDef file describing the `ruian-links.ttl`. 

- The DataDef expects a SPARQL endpoint with the `ruian-links.ttl` data filled in at URL
  `http://localhost:3030/foo/query`. Use Jena Fuseki or any other triplestore+sparql server.