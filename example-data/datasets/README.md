# Andruian testing datasets

## incremental
- Datasets intended to test incremental indexing.
- Upload `streets-starting-with-a-1.ttl` to triple store, perform indexing. 383 places should get indexed.
- Upload `streets-starting-with-a-2.ttl` to triple store, perform incremental indexing. 714 places should get indexed.

## sizes
- Datasets with increasing sizes.
- The name (number) of each dataset reflects the number of _source_ classes that are created. That is, size "10" means 
  there are 10 source classes linking to 10 intermediate classes, linking to 10 more intermediate classes, linking to 
  10 RÚIAN classes. 
- See [construct-query.sparql](construct-query.sparql) to see how they were created (with slight adjustments) 