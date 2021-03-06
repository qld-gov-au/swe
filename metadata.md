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

#### All other pages
```html
<title>TITLE | FRANCHISE | Queensland Government</title>
```

* Replace TITLE with the title of the page. This is the same title used in the main heading h1 on the page.
* Replace FRANCHISE with the name of your franchise.
* Queensland Government is to be appended to all page titles.
* This will be repeated in DCTERMS.title (see below) without the 'Queensland Government' suffix.

### Description (common)
```html
<meta name="description" content="DESCRIPTION" />
```
* Replace DESCRIPTION with a short description of the page. This may be used by external services when linking back.
* This will be repeated in DCTERMS.description (see below).

### Keywords
```html
<meta name="keywords" content="KEYWORDS" />
```
* Keywords are OPTIONAL. Replace KEYWORDS with words or short phrases. Separate terms and phrases with commas.

## Dublin Core and AGLS metadata
```html
<link rel="schema.DCTERMS" href="http://purl.org/dc/terms/" />
<link rel="schema.AGLSTERMS" href="http://www.agls.gov.au/agls/terms/" />
```
* These links declare the AGLS and Dublin Core namespaces used in the following metadata.

### Creator, publisher, created and modified dates
#### Creator
```html
<meta name="DCTERMS.creator" scheme="AGLSTERMS.GOLD" content="c=AU; o=The State of Queensland; ou=DEPARTMENT NAME; ou=UNIT NAME" />
```
* Replace DEPARTMENT NAME and UNIT NAME with the names of the organisational units (ou) that created the content.
* You do not need to change this metadata if the department/unit changes their name later.

#### Publisher
```html
<meta name="DCTERMS.publisher" scheme="AGLSTERMS.AglsAgent" content="corporateName=The State of Queensland; jurisdiction=Queensland" />
```
* The publisher is always Queensland Government. Include this line without changing it.

#### Date (created, modified)
```html
<meta name="DCTERMS.created" content="YYYY-MM-DD" />
<meta name="DCTERMS.modified" content="YYYY-MM-DD" />
```
* The dates that the page was created and updated.
* Set the created date once, when the page is first created.
* Update the modified date when the page is changed (change the Last updated date in the page footer at the same time!)
* Dates are assumed to be in local time---AEST (Australian Eastern Standard Time) is UTC+10:00

### Titles and descriptions (Dublin Core)
#### Title
##### Landing pages
```html
<meta name="DCTERMS.title" content="FRANCHISE" />
```
* Replace FRANCHISE with the name of your franchise. On landing pages, the main page heading (i.e. h1) is the franchise name. 
##### All other pages
```html
<meta name="DCTERMS.title" content="TITLE | FRANCHISE" />
```
* Replace TITLE with the main page heading (i.e. h1). Replace FRANCHISE with the name of your franchise. 

Alternative title
```html
<meta name="DCTERMS.alternative" content="ALTERNATIVE TITLE" />
```
* **Alternative titles are optional.** Repeat this line for each alternative title.
* If the document has a common name, you may use that as an alternative title.

#### Description
##### All pages
```html
<meta name="DCTERMS.description" content="DESCRIPTION" />
```
* Repeat the description here. This is a fallback for tools that look for Dublin Core metadata and ignore the common 'description' meta tag.

### Cataloguing and classification
#### Subject
```html
<meta name="DCTERMS.subject" scheme="AGLSTERMS.APAIS" content="SUBJECT" />
```

#### Function
```html
<meta name="AGLSTERMS.function" scheme="AGLSTERMS.AGIFT" content="FUNCTION" />
```
* AGLS requires at least one subject or function. You may include both.
* Multiple subjects should be separated with semi-colons.
* Additional subject and/or function values may be included using different schemes, but please include APAIS or AGIFT terms first.
*  [APAIS (Australian Public Affairs Information Service)](http://www.nla.gov.au/apais/thesaurus/index.html)
*  [AGIFT (Australian Governments' Interactive Functions Thesaurus)](http://agift.naa.gov.au/)

### Identifier
```html
<meta name="DCTERMS.identifier" scheme="DCTERMS.URI" content="http://www.qld.gov.au/" />
```
* Include the full URL of the web page. Pages published on www.qld.gov.au can use an SSI that automatically provides the correct identifier:
```html
<!--#include virtual="/assets/includes/global/head-meta-identifier.html"-->
```

### Document and service types
```html
<meta name="DCTERMS.type" scheme="DCTERMS.DCMIType" content="Text" />
```
Choose the most appropriate type value (usually 'Text').

| Type        | Suggested use
| ------------- | ------------- 
| Collection      | use on landing, theme and topic pages
| Dataset      | Not applicable
| Event      | use for web pages that describe an event (see also coverage)
| Image      | Not applicable
| InteractiveResource      | Flash games, educational resources, etc.
| MovingImage      | Not applicable
| PhysicalObject      | Not applicable
| Service      | Use for online services, qualify with AGLSTERMS.serviceType
| Software      | Not applicable
| Sound      | Not applicable
| Text      | use for content and guide pages, except events and services

[DCMI Type Vocabulary](http://dublincore.org/documents/2010/10/11/dcmi-type-vocabulary/)

#### Landing, theme and topic pages
```html
<meta name="DCTERMS.type" scheme="DCTERMS.DCMIType" content="Collection" />
<meta name="AGLSTERMS.aggregationLevel" content="collection"/>
<meta name="AGLSTERMS.documentType" scheme="AGLSTERMS.agls-document" content="index" />
```
* Change DCTERMS.type to Collection and specify AGLSTERMS.aggregationLevel and AGLSTERMS.documentType as indicated.
* AGLSTERMS.aggregationLevel defaults to 'item' and does not need to be specified on other pages.

##### Content pages
```html
<meta name="DCTERMS.type" scheme="DCTERMS.DCMIType" content="Text" />
<meta name="AGLSTERMS.documentType" scheme="AGLSTERMS.agls-document" content="guidelines" />
```
* Choose the best match from the AGLS Document Vocabulary Encoding Scheme
* Do not use more than one term. Do not make up your own terms.
* If in doubt, choose 'guidelines'

###### Time (temporal coverage)
```html
<meta name="DCTERMS.temporal" content="name=Perth International Arts Festival, 2000; start=2000-01-26; end=2000-02-20;" />
```
[DCMI Period](http://dublincore.org/documents/dcmi-period/)

###### Place (spatial coverage)
(TBA see getinvolved consultation metadata form)

[DCMI Box](http://dublincore.org/documents/dcmi-box/) and [DCMI Point](http://dublincore.org/documents/dcmi-point/)

#### Service pages and applications
```html
<meta name="DCTERMS.type" scheme="DCTERMS.DCMIType" content="Service" />
<meta name="AGLSTERMS.serviceType" scheme="AGLSTERMS.agls-service" content="transactions" />
```
* Choose the best match from the AGLS Service Vocabulary Encoding Scheme
* Do not use more than one term. Do not make up your own terms.
* If you cannot find a better match, use 'transactions'.

### Intended audience
```html
<meta name="DCTERMS.audience" scheme="AGLSTERMS.agls-audience" content="all" />
```

* Terms must be chosen from the AGLS Audience Vocabulary Encoding Scheme.
* Choose the best match. Do not make up your own terms. Separate multiple terms with semi-colons.
* Specify the audience the document was written for.
* If the document is about an audience, use subject. For example, a page written for parents of children with autism would use 'parents' as the subject, NOT 'people with disabilities', and should use 'Children with disabilities' as a subject (from APAIS).
* If the document is generally for anybody, use 'all'.

### Converage
```html
<meta name="DCTERMS.coverage" scheme="AGLSTERMS.AglsJuri" content="Queensland" />
```

### Content licence
```html
<meta name="DCTERMS.license" scheme="DCTERMS.URI" content="https://creativecommons.org/licenses/by/4.0/" />
```
(GILF has been superseded by [AusGOAL](http://www.ausgoal.gov.au/))

## Notes
### Page titles

Page titles appear in multiple places within each web page.

**On landing pages** the page title is always the franchise name and appears:

 1. as the first part of the <title> element along with 'Queensland Government'
 2. in the metadata as DCTERMS.title
 3. as the main content heading h1
 4. at the end of the breadcrumb
 5. in variables passed to:
  
    
    a. web analytics scripts
    
    b. the page feedback form
    
    c. the share script

**On other pages** the page title appears:

 1. as the first part of the <title> element, along with the franchise name and 'Queensland Government'
 2. in the metadata as DCTERMS.title, along with the franchise name
 3. as the main content heading h1
 4. at the end of the breadcrumb
 5. in variables passed to:
  
    a. web analytics scripts
    
    b. the page feedback form
    
    c. the share script
