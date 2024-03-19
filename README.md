# N3

The N3 library is an implementation of the [RDF.js low-level specification](http://rdf.js.org/) that lets you handle [RDF](https://www.w3.org/TR/rdf-primer/) in JavaScript easily.
It offers:

- **Parsing** triples/quads from
  [Turtle](https://www.w3.org/TR/turtle/),
  [TriG](https://www.w3.org/TR/trig/),
  [N-Triples](https://www.w3.org/TR/n-triples/),
  [N-Quads](https://www.w3.org/TR/n-quads/),
  [RDF*](https://blog.liu.se/olafhartig/2019/01/10/position-statement-rdf-star-and-sparql-star/)
  and [Notation3 (N3)](https://www.w3.org/TeamSubmission/n3/)
- **Writing** triples/quads to
  [Turtle](https://www.w3.org/TR/turtle/),
  [TriG](https://www.w3.org/TR/trig/),
  [N-Triples](https://www.w3.org/TR/n-triples/),
  [N-Quads](https://www.w3.org/TR/n-quads/)
  and [RDF*](https://blog.liu.se/olafhartig/2019/01/10/position-statement-rdf-star-and-sparql-star/)
- **Storage** of triples/quads in memory

## Usage

```shell
$ deno
> import * as N3 from 'https://esm.sh/gh/doga/N3@1.17.2/mod.mjs';
undefined
> const { DataFactory } = N3;
const { namedNode, literal, defaultGraph, quad } = DataFactory;
const myQuad = quad(
  namedNode('https://person.example/#me'), // Subject
  namedNode('http://xmlns.com/foaf/0.1/givenName'),    // Predicate
  literal('Xyz', 'en'),                              // Object
  defaultGraph(),                                      // Graph
);
console.log(myQuad.termType);              // Quad
console.log(myQuad.value);                 // ''
console.log(myQuad.subject.value);         // https://person.example/#me
console.log(myQuad.object.value);          // Xyz
console.log(myQuad.object.datatype.value); // http://www.w3.org/1999/02/22-rdf-syntax-ns#langString
console.log(myQuad.object.language);       // en
Quad

https://person.example/#me
Xyz
http://www.w3.org/1999/02/22-rdf-syntax-ns#langString
en
undefined
>
```

## Forked

This is a fork of [dfjs/N3.js](https://github.com/rdfjs/N3.js).

∎
