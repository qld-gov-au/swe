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

* Some metadata is captured through standard HTML markup---for example, document language.
* Other metadata may be repeated visibly in the page content---for example, modified date.

## Common metadata

### Language

```html
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en-AU" lang="en-AU">
```

* Specify the primary language of the document using @xml:lang and @lang.
* en-AU is recommended for Australian English.

### Title
#### Landing pages
```html
<title>FRANCHISE | Queensland Government</title>
```

* On franchise landing pages the franchise name is the page title.
* Replace FRANCHISE with the name of your franchise. The main heading h1 on the landing page will also be the franchise name.
* Queensland Government is to be appended to all page titles.
* This will be repeated in DCTERMS.title (see below) without the 'Queensland Government' suffix.

