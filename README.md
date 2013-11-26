# Introduction

This repository contains a list of queries illustrating how to use the ChEMBL SPARQL enpoint. If you are new to the
semantic web, you can [follow a tutorial](http://www.cambridgesemantics.com/semantic-university/introduction-to-the-semantic-web). If you have some knowledge about SQL and relational database already, the transition to SPARQL should be easy, first read the introduction below and you can directly get started!

### RDF

RDF stands for Resource Description Framework. Briefly, it is a conceptual way of representing data as a graph, as opposite to relational databases, focusing on relations. Within RDF, the information is encoded as triples, and identifiers are Universal Resource Identifiers (URI or web addresses). Representing data as a graph is interesting because it simplifies the integration of information from different sources. URIs guarantees the uniqueness of resources and allow you to simply explore them with your web browser.

### SPARQL

SPARQL is a language used to query RDF data. It is fairly similar to SQL, yet better standardised and more flexible to query multiple data sources or *services* in the same time. A *SPARQL endpoint* is a web address you use to access the RDF data and run SPARQL queries. The ChEMBL SPARQL enpoint is located at http://www.ebi.ac.uk/rdf/services/chembl/sparql

### What should I consider using the SPARQL endpoint?

Semantic web technologies provide two main advantages. First, they remove the need to maintain, update, download, parse and handle flat files or databases. You can query the ChEMBL data directly from the web, in a fully automated way. RDF helps you to focus entirely on the query, where the real scientific value is.

Secondly, it becomes easier to integrate the data from another provider. For instance, when you analyse ChEMBL data, you may realise that it would be interesting to combine your current results with gene expression or pathway information. SPARQL allows you to do this very easily, as illustrated in the example queries.

### How do I run the queries?

You can directly copy and paste the queries from the files in the web form on the [SPARQL endpoint](http://www.ebi.ac.uk/rdf/services/chembl/sparql). Do not include the commented lines, starting with the symbol `#` in very first line of query, the endpoint does not support them yet. You can put it from 2nd line.

It is also possible to run the queries from R or with command lines. More examples will come to demonstrate this feature. Finally, you can also [check the ChEMBL endpoint documentation](http://www.ebi.ac.uk/rdf/services/chembl/sparql) or [contact us](http://www.ebi.ac.uk/rdf/documentation/chembl) if you are facing problems.

# SPARQL queries to execute on ChEMBL SPARQL endpoint

### A. Simple queries

1. Retrieve trade name of ChEMBL molecule having ChEMBL-id "CHEMBL192". [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/tradeNameOf192Molecule.rq) or [see it live](http://tinyurl.com/o3uzcol)
2. Retrieve molecular formula of ChEMBL molecule having ChEMBL-id "CHEMBL192". [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/molFormulaof192Molecule.rq) or [see it live](http://tinyurl.com/pljpjwn)
3. Retrieve rotational bond of ChEMBL molecule having ChEMBL-id  "CHEMBL192". [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/rotbonOf192Molecule.rq) or [see it live](http://tinyurl.com/p8rmghh)
4. Retrieve ChEMBL molecule using the trade name, here trade name is "sildenafil". [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/moleculeSourceForTradeName.rq) or [see it live](http://www.ebi.ac.uk/rdf/services/chembl/sparql?query=PREFIX+rdf%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+owl%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E%0D%0APREFIX+dc%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcterms%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dbpedia2%3A+%3Chttp%3A%2F%2Fdbpedia.org%2Fproperty%2F%3E%0D%0APREFIX+dbpedia%3A+%3Chttp%3A%2F%2Fdbpedia.org%2F%3E%0D%0APREFIX+foaf%3A+%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+skos%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0APREFIX+cco%3A+%3Chttp%3A%2F%2Frdf.ebi.ac.uk%2Fterms%2Fchembl%23%3E%0D%0A%0D%0A%0D%0ASELECT+%3Fmolecule%0D%0AWHERE+{%0D%0A++%3Fmolecule+skos%3AaltLabel+%3Fname.%0D%0A++FILTER+regex%28%3Fname+%2C%22sildenafil%22%2C+%27i%27%29%0D%0A}&render=HTML&limit=100&offset=0#lodestart-sparql-results)
5. Retrieve the ChEMBL molecules having molecular formula is combination of “C22H30N6O4S”. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/sourceForMolecularFormula.rq) or [see it live](http://tinyurl.com/qzmlsnq)
6. Retrieve ChEMBL molecules having molecular weight between 500 and 900. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/queries/molWeightBased.rq) or [see it live](http://www.ebi.ac.uk/rdf/services/chembl/sparql?query=PREFIX+rdf%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+owl%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E%0D%0APREFIX+dc%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcterms%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+skos%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0APREFIX+cco%3A+%3Chttp%3A%2F%2Frdf.ebi.ac.uk%2Fterms%2Fchembl%23%3E%0D%0A%0D%0A%0D%0ASELECT+%3FChEMBL_id+%3FmolWeight%0D%0AWHERE{%0D%0A++%3Fmolecule+rdfs%3AsubClassOf+cco%3ASubstance.%0D%0A++%3Fmolecule+rdfs%3Alabel+%3FChEMBL_id.%0D%0A++%3Fmolecule+%3Fprop+%3FcompProp.%0D%0A++%3FcompProp+%3Chttp%3A%2F%2Fsemanticscience.org%2Fresource%2FSIO_000300%3E+%3FmolWeight.%0D%0A++FILTER+regex%28%3FcompProp%2C%22full_mwt%22%2C+%22i%22%29%0D%0A++FILTER+%28%28+500+%3C+%3FmolWeight%29+%26%26+%28%3FmolWeight+%3C+900%29%29%0D%0A}&render=HTML&limit=25&offset=0#lodestart-sparql-results)

### B. Moderate queries 

1. Retrieve journal and published date for ChEMBL molecule, here molecule is "CHEMBL282282". [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/compoundJurDate.rq) or [see it live](http://www.ebi.ac.uk/rdf/services/chembl/sparql?query=PREFIX+rdf%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+owl%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E%0D%0APREFIX+dc%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcterms%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dbpedia2%3A+%3Chttp%3A%2F%2Fdbpedia.org%2Fproperty%2F%3E%0D%0APREFIX+dbpedia%3A+%3Chttp%3A%2F%2Fdbpedia.org%2F%3E%0D%0APREFIX+foaf%3A+%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+skos%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0APREFIX+cco%3A+%3Chttp%3A%2F%2Frdf.ebi.ac.uk%2Fterms%2Fchembl%23%3E%0D%0A%0D%0A%0D%0A%0D%0APREFIX+rdf%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+owl%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E%0D%0APREFIX+dc%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcterms%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dbpedia2%3A+%3Chttp%3A%2F%2Fdbpedia.org%2Fproperty%2F%3E%0D%0APREFIX+dbpedia%3A+%3Chttp%3A%2F%2Fdbpedia.org%2F%3E%0D%0APREFIX+foaf%3A+%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+skos%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0APREFIX+cco%3A+%3Chttp%3A%2F%2Frdf.ebi.ac.uk%2Fterms%2Fchembl%23%3E%0D%0APREFIX+bibo%3A+%3Chttp%3A%2F%2Fpurl.org%2Fontology%2Fbibo%2F%3E%0D%0A%0D%0A%0D%0ASELECT+DISTINCT+%3Fjournal+%3Ftitle+%3Fdate%0D%0AWHERE%7B+%0D%0A++%3Fmolecule+rdfs%3AsubClassOf+cco%3ASubstance.+%0D%0A++%3Fmolecule+rdfs%3Alabel+%22CHEMBL282282%22.%0D%0A++%3Fmolecule+cco%3AhasDocument+%3Fdoc.%0D%0A++%3Fdoc+cco%3AhasJournal+%3Fjournal.%0D%0A++%3Fjournal+dcterms%3Atitle+%3Ftitle.%0D%0A++%3Fdoc+dcterms%3Adate+%3Fdate.%0D%0A%7D&render=HTML&limit=25&offset=0#lodestart-sparql-results) 
- Retrieve ChEMBL molecules having activity stndard type "IC50" and standard unit "nM". [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/queries/IC50Compounds_1.rq) or [see it live](http://tinyurl.com/pebrtph)
- Retrieve target types available in ChEMBL rdf triple store. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/targetType.rq) or [see it live](http://tinyurl.com/p5ranmk)
- Retrieve substance types having target type "cell-line". [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/substanceTypeToCell-line.rq) or [see it live](http://tinyurl.com/qh7shqb)
- Retrieve ChEMBL molecules activity details for all target. [file]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/compoundActDetails.rq) or [see it live](http://tinyurl.com/of6eybt)
- Retrieve ChEMBL molecules activity details for a target, and target is Human PDE5 (CHEMBL1827). [file]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/detailsForTarget.rq) or [see it live](http://tinyurl.com/nel7srs)
- Retrieve ChEMBL molecules targeting "Bacteria". [file]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/bacterialTargetData.rq) or [see it live](http://tinyurl.com/q2rrzma)
- Retrieve ChEMBL molecules targeting “Firefly Luciferase”. [file]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/compoundToFirLuciferase.rq) or [see it live](http://tinyurl.com/pbvfjyu)
- Retrieve target details, uniprot_reference and sequences for proteins target. [file]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/compoundDetailsForProteinTar.rq)or [see it live](http://tinyurl.com/nv9lqyl)
- Retrieve ChEMBL molecules activity details for all targets containing a protein of interest, and protein of interest is human M2 muscarinic receptor (P08172). [file]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/queries/P08172CompActAssTarDet.rq) or [see it live](http://tinyurl.com/qzbepv7)
- Retrieve approved drug for Mycobacterium tuberculosis target. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/queries/AppDrgMybTub.rq) or [see it live](http://www.ebi.ac.uk/rdf/services/chembl/sparql?query=PREFIX+rdf%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+owl%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E%0D%0APREFIX+dc%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcterms%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+skos%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0APREFIX+cco%3A+%3Chttp%3A%2F%2Frdf.ebi.ac.uk%2Fterms%2Fchembl%23%3E%0D%0A%0D%0A%0D%0ASELECT+DISTINCT+%3Fdrug%0D%0AWHERE{%0D%0A++%3Fmolecule+rdfs%3AsubClassOf+cco%3ASubstance.%0D%0A++%3Fmolecule+cco%3AhighestDevelopmentPhase+%224%22^^xsd%3Ainteger.%0D%0A++%3Fmolecule+skos%3AprefLabel+%3Fdrug.%0D%0A++%3Fmolecule+cco%3AhasActivity+%3Fact.%0D%0A++%3Fact+cco%3AhasAssay+%3Fass.%0D%0A++%3Fass+cco%3AhasTarget+%3Ftar.%0D%0A++%3Ftar+cco%3AtargetType+%22SINGLE+PROTEIN%22.%0D%0A++%3Ftar+cco%3AorganismName+%22Mycobacterium+tuberculosis%22.%0D%0A++%3Ftar+cco%3AhasTargetComponent+%3Ftc.%0D%0A++%3Ftc+skos%3AexactMatch+%3FdbXref+.%0D%0A}+ORDER+by+%3Fdrug%0D%0A%0D%0A&render=HTML&limit=25&offset=0#lodestart-sparql-results)


Note: Try to avoid the use of FILTER construct in SPARQL query, because it takes more time in execution.


# SPARQL queries for metadata

 If you are new for a RDF triple store then you can start with these metadata queries. Because these queries work on any SPARQL endpoint. It will help you to explore the unfamiliar triple store.  
 
1. [Retrieve all available triples from triple store]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/metadataQuery1.rq)
- [Retrieve types defined in triple store]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/metadataQuery2.rq)
- [Retrieve properties defined in triple store]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/propertiesMetadata.rq)
- [Retrieve values has been associated with given property]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/propertyValuesMetadata.rq)
- [Retrieve triples where subjects are label]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/metadataQuery4.rq)
- [Retrive all declared classes]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/allclassesMetadata.rq)
- [Retrieve triples which is subClassOf of class]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/metadataQuery3.rq)
- [Retrieve properties have been associated for a given class]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/classPropertiesMetadata.rq)
- [Retrieve subclasses descendants of a given class]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/descendatsClassesMetadata.rq)
- [Retrieve the relation with source (URI)]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/describeMetadata.rq)
- [Retrieve the service description of the endpoint]( https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/metadataQueries/serviceDescriptionMetadata.rq )


# ChEMBL federated or others endpoint service related SPARQL queries 

### Execute on ChEMBL SPARQL endpoint
1. Retrieve location of Mycobacterium tuberculosis proteins which is targeted by ChEMBL molecules. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/federatedAndOthersEndpointQueries/locMycTubProtComp.rq) or [see it live](http://tinyurl.com/o5f9mcd)
2. Retrieve pathway of Mycobacterium tuberculosis proteins which is targeted by ChEMBL molecules. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/federatedAndOthersEndpointQueries/pathMycTubProtComp.rq) or [see it live](http://tinyurl.com/qa2hyln)
3. Retrieve the proteins and their sequence involved in Alzheimer disease. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/federatedAndOthersEndpointQueries/proteinRelatedToAlzheimerChEMBL_up.rq) or [see it live](http://tinyurl.com/q6bvutv)
4. Retrieve activities of proteins involved in Alzheimer disease. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/federatedAndOthersEndpointQueries/actAlz.rq) or [see it live](http://tinyurl.com/nbhj9do) 
5. Retrieve active pathway of proteins involved in Alzheimer disease. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/federatedAndOthersEndpointQueries/pathAlzProt.rq) or [see it live](http://tinyurl.com/ove9vy6) 

### Execute on UniProt endpoint
1. Retrieve known diseases from uniprot. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/federatedAndOthersEndpointQueries/knownDisUp.rq) or [see it live](http://tinyurl.com/pudqtkl)
2. Retrieve total number of known diseases in uniprot. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/federatedAndOthersEndpointQueries/totKnownDisUp.rq) or [see it live](http://tinyurl.com/pnhmoto)
3. Retrieve the proteins and their sequence involved in Alzheimer disease. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/tree/master/federatedAndOthersEndpointQueries/proteinsRelatedToAlzheimerUp.rq) or [see it live](http://tinyurl.com/nfnw6yx)
4. Retrieve molecular function and biological process associated with Alzheimer disease proteins. [file](https://github.com/Ashwini607/ChEMBL-RDF-Queries/blob/master/federatedAndOthersEndpointQueries/protAlzMolBio.rq) or [see it live](http://tinyurl.com/qcxtprt) 
