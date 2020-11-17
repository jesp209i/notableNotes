---
title: NoSQL - MongoDB
created: '2020-11-17T08:11:26.897Z'
modified: '2020-11-17T09:59:49.757Z'
---

# NoSQL - MongoDB
## Datamodelling
- embedded document
  * Use when:
    - Child data belongs to parent (1:1)
    - Sub-documents are small in size
    - Hierarchial structures
  * Caution:
    - Growing data
    - Unnecessary data sent with every query
    - Redundant data
- linking or referencing between documents
  * Use when:
    - M:N relationship
    - Sub-documents 
- (continued on Bernies slides)

## Versioning of schemas
If you change data structure, add `schema_version` to your changes document:
 ```JSON
 // Old version
 {
   _id : 123,
   name: "Hans Andersen",
   mobile: "233423423423",
   work_phone: "34563456456"
 }

// new version
{
  _id: 537,
  name: "Ada Wolf",
  schema_version: 2.0,
  contact : {
    mobile: "456456456",
    work_phone: "34578753",
    email: "ada@wolf.com"
  }
}
```

## Replication MongoDB
Primary recieves documents and changes.... data to secondary nodes.

If primary fails, the secondary will elect a new primary.

You can read from (but not write to) a secondary.

Async replication: Write concern

replica set is how you setup replication.

## Index in MongoDB
There is an unique index on the `_id` field by default.

- you can add indexes on other fields.
- you can add full text search indexes.
- you can add location data index - "geospacial"


