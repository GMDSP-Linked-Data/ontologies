Ontologies
==========

The Greater Manchester Data Synchronization Programme has defined various schemas (ontologies) which should be adhered to when defining datasets to ensure maximum interoperability.  The ontologies define the types of things which exist in these datasets and the properti
es they can have. The ontologies are described as RDF Schemas and are in the turtle RDF format.

Example
-------

Here is a description of a recycling centre:

    <http://data.gmdsp.org.uk/id/salford/recycling/morrison-superstore--bentcliffe-way--eccles>
            a       <http://data.gmdsp.org.uk/def/council/recycling/RecyclingSite> ;
            <http://www.w3.org/2000/01/rdf-schema#label>
                    "Recycling Site at Morrison Superstore, Bentcliffe Way, Eccles" ;
            <http://data.gmdsp.org.uk/def/council/recycling/recyclingType>
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/cartons> , 
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/cardboard>, 
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/shoes>,
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/paper>, 
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/plastic>,
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/cans>,
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/textiles>,
                    <http://data.gmdsp.org.uk/def/council/recycling/recycling-type/glass> ;
            <http://data.ordnancesurvey.co.uk/ontology/spatialrelations/easting>
                    "377734" ;
            <http://data.ordnancesurvey.co.uk/ontology/spatialrelations/northing>
                    "398415" ;
            <http://www.w3.org/2003/01/geo/wgs84_pos#lat>
                   "53.4819792797"^^<http://www.w3.org/2001/XMLSchema#double> ;
            <http://www.w3.org/2003/01/geo/wgs84_pos#long>
                   "-2.33698910835"^^<http://www.w3.org/2001/XMLSchema#double> ;
            <http://www.w3.org/2006/vcard/ns#hasAddress>
                   <http://data.gmdsp.org.uk/id/salford/recycling/address/recycling-point-7-irwell-place-eccles-manchester-m30-0fh> .
    
    <http://data.gmdsp.org.uk/id/salford/recycling/address/recycling-point-7-irwell-place-eccles-manchester-m30-0fh>
            a       <http://www.w3.org/2006/vcard/ns#Location> ;
           <http://www.w3.org/2000/01/rdf-schema#label>
                    "Address of Recycling Site at Morrison Superstore, Bentcliffe Way, Eccles" ;
            <http://data.ordnancesurvey.co.uk/ontology/postcode/postcode>
                    <http://data.ordnancesurvey.co.uk/id/postcodeunit/M300FH> ;
            <http://www.w3.org/2006/vcard/ns#postal-code>
                "M30 0FH" ;
            <http://www.w3.org/2006/vcard/ns#street-address>
                   "Recycling Point 7 Irwell Place Eccles Manchester M30 0FH " .

It may help to look at the ontology and concept scheme in the recycling folder while reading the following description.  
The first group of triples have a common subject with id [http://data.gmdsp.org.uk/id/salford/recycling/morrison-superstore--bentcliffe-way--eccles](http://data.gmdsp.org.uk/id/salford/recycling/morrison-superstore--bentcliffe-way--eccles "Link to recycling centre") which is of type [RecyclingSite](http://data.gmdsp.org.uk/def/council/recycling/RecyclingSite "Definition of a Recycling Site"). It has the human readable [label](http://www.w3.org/2000/01/rdf-schema#label "Definition of Label") "Recycling Site at Morrison Superstore, Bentcliffe Way, Eccles". It has the property [recyclingType](http://data.gmdsp.org.uk/def/council/recycling/recyclingType "Definition of recycling type") with values defined in the concept scheme, eg. [http://data.gmdsp.org.uk/def/council/recycling/recycling-type/cartons](http://data.gmdsp.org.uk/def/council/recycling/recycling-type/cartons "Definition of carton recycling type"). It has several properties which are defined in other ontologies, eg. [Eastings](http://data.ordnancesurvey.co.uk/ontology/spatialrelations/easting "Definition of Eastings from OS"). The final property listed is [http://www.w3.org/2006/vcard/ns#hasAddress](http://www.w3.org/2006/vcard/ns#hasAddress "Defintion of hasAddress property from the vcard ontology") from the vCard ontology which has the value [http://data.gmdsp.org.uk/id/salford/recycling/address/recycling-point-7-irwell-place-eccles-manchester-m30-0fh](http://data.gmdsp.org.uk/id/salford/recycling/address/recycling-point-7-irwell-place-eccles-manchester-m30-0fh "Address subject for a recycling centre") and if we look at the second group of triples we can see that this is the subject for a set of triples with type [http://www.w3.org/2006/vcard/ns#street-address](http://www.w3.org/2006/vcard/ns#street-address "Definition of streetAdress property in vcard ontology") ie. it describes the address for the recycling site.

Defining types, properties and values
-------------------------------------

A type URI has the form http://data.gmdsp.org.uk/def/council/{dataset-type}/{SubjectType} eg http://data.gmdsp.org.uk/def/council/recycling/RecyclingSite>. The dataset-type is 'recycling' and the SubjectType is RecyclingSite. The dataset-type is lower case and dasherized. The SubjectType is camel cased with a capital letter at the beginning.

A property URI has the form http://data.gmdsp.org/def/council/{dataset-type}/{propertyType}. eg http://data.gmdsp.org.uk/def/council/recycling/recyclingType. The dataset-type is 'recycling' and the propertyType is 'recyclingType'. The dataset-type is lower case and dasherized. The propertyType is camel cased and begins with a lower case letter.

A property value URI has the form http://data.gmdsp.org.uk/def/council/{dataset-type}/{property-type}/{property-value} eg. http://data.gmdsp.org.uk/def/council/recycling/recycling-type/cartons. The dataset-type is 'recycling', the property-type is 'recycling-type' and the property-value is 'cartons'. The dataset-type is lower case and dasherized. Te property-type is lower case and dasherized. The property-value is lower case and dasherized.

Licence
-------
[OGL v2](http://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/ "UK Open Government Licence version 2")
