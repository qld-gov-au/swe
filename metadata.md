# How to implement metadata on SWE pages

This page details metadata in HTML documents.

Metadata is stored in meta tags within the head of each web pages. Use of microdata, RDFa (or other formats) has not yet been considered.

Metadata needs to be recorded against each page. It is not embedded in the global includes.

## References

* [Metadata (IS34)](https://www.qgcio.qld.gov.au/qgcio/architectureandstandards/informationstandards/current/Pages/Metadata.aspx)

* [AGLS Metadata Standard](http://www.agls.gov.au/) (read the Usage Guide in particular)

* [DCMI Metadata Terms](http://dublincore.org/documents/dcmi-terms/) (Dublin Core Metadata Initiative)

* [APAIS thesaurus](http://www.nla.gov.au/apais/thesaurus/search.html) (Australian Public Affairs Information Service)

* [AGIFT](http://agift.naa.gov.au/) (Australian Governments' Interactive Functions Thesaurus)

## Syntax

meta tags represent key-value pairs.

```html
<meta name="KEY" content="VALUE" />
```

Some metadata is captured through standard HTML markup---for example, document language.

Other metadata may be repeated visibly in the page content---for example, modified date.
