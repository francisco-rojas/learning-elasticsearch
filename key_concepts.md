# Key Concepts

#### Documents
Elasticsearch is document oriented, it stores and indexes entire objects or documents. Instead of using rows and columns like RDMS (Relational Database Management Systems).

#### JSON Storage
Elasticsearch uses JSON as the serialization format for documents.

#### Index (noun) vs Index (verb) vs Inverted index vs Indexing
The act of storing data in Elasticsearch is called indexing.
- **Index (noun):** An index is like a database in a RDMS. It is the place to store related documents. The plural of index is indices or indexes.
- **Index (verb):** To index a document is to store a document in an index (noun) so that it can be retrieved and queried. It is much like the INSERT keyword in SQL except that, if the document already exists, the new document would replace the old.  
- **Inverted index:** RDMS add an index, such as a B-tree index, to specific columns in order to improve the speed of data retrieval. Elasticsearch and Lucene use a structure called an inverted index for exactly the same purpose. By default, every field in a document is indexed (has an inverted index) and thus is searchable. A field without an inverted index is not searchable.

#### Storage Hierarchy 
An Elasticsearch cluster can contain multiple indices, which in turn contain multiple documents, and each document has multiple fields.
```
    -----------
   |  cluster  |
    -----------
           ----------------     
          |  Index (noun)  |      
           ----------------     
                    --------------       
                   |   Document   |      
                   |   field1     |      
                   |   field2     |      
                    --------------   
```
Sample Document:

```json
{
    "email":          "john@smith.com",
    "first_name":     "John",
    "last_name":      "Smith",
    "info": {
        "bio":        "Eco-warrior and defender of the weak",
        "age":        25,
        "interests":  [ "dolphins", "whales" ]
    },
    "join_date":      "2014/05/01"
}
```

#### Mapping
Mapping is the process of defining how a document, and the fields it contains, are stored and indexed. It is similar to a database schema.
A mapping definition has:

- Metadata fields: Metadata fields are used to customize how a document’s associated metadata is treated. Examples of metadata fields include the document’s _index, _id, and _source fields. 
- Fields or properties: A mapping contains a list of fields or properties pertinent to the document, and each field has a data type (e.g. string, date, etc.).
- Mappings can be either dynamic (automatic) or explicit (you specify the mapping)
- Mappings are attached to an index and documents stored in the index follow the specified mapping. 

#### Data Types
- Each field has a field data type, or field type. This type indicates the kind of data the field contains, such as strings or boolean values, and its intended use.
- In Elasticsearch, arrays do not require a dedicated field data type. Any field can contain zero or more values by default, however, all values in the array must be of the same field type.
- It is often useful to index the same field in different ways for different purposes. For instance, a string field could be mapped as a text field for full-text search, and as a keyword field for sorting or aggregations. 
- An alias mapping defines an alternate name for a field in the index. The alias can be used in place of the target field in search requests

#### Other Resources
- Removal of mapping types: https://www.elastic.co/guide/en/elasticsearch/reference/7.9/removal-of-types.html
- Mappings: https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html
- Glosary: https://www.elastic.co/guide/en/elasticsearch/reference/current/glossary.html#glossary
