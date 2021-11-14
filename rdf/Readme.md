# RDF

## What is RDF
Resource Description Framework (RDF) is a foundation for processing metadata; it provides interoperability between applications that exchange machine-understandable information on the Web. RDF emphasizes facilities to enable automated processing of Web resources. RDF can be used in a variety of application areas; for example: in resource discovery to provide better search engine capabilities, in cataloging for describing the content and content relationships available at a particular Web site, page, or digital library, by intelligent software agents to facilitate knowledge sharing and exchange, in content rating, in describing collections of pages that represent a single logical "document", for describing intellectual property rights of Web pages, and for expressing the privacy preferences of a user as well as the privacy policies of a Web site. RDF with digital signatures will be key to building the "Web of Trust" for electronic commerce, collaboration, and other applications. 

## An example of Data Graph
![Data Grpah](images/scene_graph.png?raw=true "Data Graph")

## RDF for Data Graph
![RDF/XML Statement](./scene.rdf?raw=true "RDF/XML Statement")

## Notation3 for Data Graph
![Notation3 Statement](./scene.rdf?raw=true "Notation3 Statement")

## Explanation
In the above example we have used two different namespaces for XML. [rdf](http://www.w3.org/1999/02/22-rdf-syntax-ns#) is used to define rdf syntaxes. [pos](https://example.org/position/1.0/) is a illustrative namespace to define predicates in data graph.
Subjects and objects are defineded using URIs.

## Sparql queries on RDF
[HP's AQL](http://sparql.org/sparql.html) is on online tool to execute queries on RDF/N3 documents. 
![Here](images/ARQ.png?raw=true "HP's ARQ.") is a screenshot of the query executer. In the input query box type the query type, type the link for RDF document in URL input box. Select the output result format and then click Get Result.
An example of query for above data graph is shown below.
### Query Statement
```sh
What all are to the right of "Boat"?
```
### Sparql Query Statement
```sh
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX pos: <https://example.org/position/1.0/>
PREFIX obj: <https://en.wikipedia.org/wiki/>

SELECT ?name WHERE {
  ?name (pos:right-of)* obj:Boat
  FILTER(?name!=obj:Boat)
}
```
### Sparql Query Ouput from [HP's AQL](http://sparql.org/sparql.html)
![Output](images/output.png?raw=true "Query Reult")
