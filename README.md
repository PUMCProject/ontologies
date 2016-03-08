# ontologies
This repository carries the set of ontologies that are used for various mapping tasks, including:

## ISO11179
This image was derived from the XMDR ISO/IEC 11179 project, and represents a slightly dated version (CD2 RC7, 2008-09-17) of ISO/IEC 11179 Edition 3 Part 3.  To date, the most significant difference between this  version and the current version (ISO/IEC 11179-3:2013(E)) is that `Characteristic` has been renamed to `Property`` in the ``Data_Element_Concept`` region.  

Additional changes:

* **ontology.owl** -- the following lines were removed from the definition of `Ontology` because they resulted in a classification error:

```xml
<rdfs:subClassOf>
      <owl:Restriction>
        <owl:onProperty rdf:resource="http://xmdr.org/ont/iso11179-3e3cd2rc7.owl#notation"/>
        <owl:cardinality rdf:datatype="http://www.w3.org/2001/XMLSchema#int"
        >1</owl:cardinality>
      </owl:Restriction>
</rdfs:subClassOf>
```
* **data.owl** -- the following lines were removed for the same reason:
 
```xml
<rdfs:subClassOf>
      <owl:Restriction>
        <owl:cardinality rdf:datatype="http://www.w3.org/2001/XMLSchema#int"
        >1</owl:cardinality>
        <owl:onProperty rdf:resource="http://xmdr.org/ont/iso11179-3e3cd2rc7.owl#notation"/>
      </owl:Restriction>
</rdfs:subClassOf>
```
* All files were converted from rdf/xml format to turtle format for readability purposes.
* The base URI was changed from `http://xmdr.org/ont/iso11179-3e3cd2rc7.owl#` to `http://iso.org/iso11179-3e3/`
* "ISO " was prefixed to the rdfs:label's to allow 11179 identifiers to be readily recognized.

Note that the root module for ISO11179 is `caDSR.ttl`, which, in turn imports all of the other modules.


