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
* An rdfs:label was created for every non-BNode subject with an 'ISO ' prefix,  to allow 11179 entities to be readily identified.

Note that the root module for ISO11179 is `caDSR.ttl`, which, in turn imports all of the other modules.

## OCRE
The Ontology of Clinical Research

It is a bit of a challenge to convince Protege to load the sources locally rather than off of the interwebs.  We removed the ".owl" suffixes on both the namespaces and the import statements, but that didn't appear to be sufficient.  We finally just blocked access to the network when loading OCRe.ttl, which forced Protege to look locally.  The ".owl" changes have been kept for the time being...

Additionally, we added  the text "OCRe " to all `rdfs:label`s in the local files and preserved the original name as `skos:prefLabel`


