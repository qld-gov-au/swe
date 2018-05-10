# 1.0 Queensland Government Website Standards
The Queensland Government’s [Information Standard 26 (IS26)](http://github.com) policy states that all public-facing Queensland Government websites must comply with the appropriate website standard.

The standards are:
* Franchise Website Standard (also known as SWE)
* Agency Website Standard (also known as the Consistent User Experience or ‘CUE’).

This document will assist agencies to understand and comply with the Franchise Website Standard.  
## 1.1	The Franchise Website Standard 

The Franchise Website Standard helps agencies contribute to a franchise model for Queensland Government online service delivery. The objective of the model is to make it easier for customers to interact with the Queensland Government by organising all citizen-facing content in a customer-centric rather than agency-centric way. This means that each franchise delivers online content for a specific topic or audience.

All Queensland Government franchise websites need to adhere to a set of guidelines that provide customers with a **single website experience (SWE)**. These guidelines form a template of technical components for use by government departments. 

This document:  
*	outlines the requirements for developing website components 
*	helps departments customise the components for their specific audience. 

The One-Stop Shop Strategy and Implementation Office (OSSSIO) is committed to meeting customers’ needs by optimising their online experience. The requirements included in this document have been developed in consultation with a wide range of stakeholders (including members of the User Interface and Mobile Applications Community of Practice) and tested by customer focus groups. 

A franchise owner may determine that their audience would benefit from a variation to a particular requirement. To request a variation, contact OSSSIO by emailing oss.products@dsiti.qld.gov.au.

# 2.0 Accessibility

The Disability Discrimination Act 1992 (Cwlth) states that all Australian websites must comply with the [W3C Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org). Queensland Government websites and websites established or commissioned by Queensland Government bodies, extranets and internet applications are also specifically mandated in IS26 to achieve conformance Level AA of these guidelines.

Note: Some agencies may require WCAG AAA Level conformance (e.g. Department of Communities, Child Safety and Disability Services). Refer to your agency’s web policy or procedure for guidelines on your conformance requirements. 

WCAG 2.0 also provides specific requirements for Rich Internet Applications. It allows for a baseline technology to be set by the site creator (e.g. JavaScript) but does not remove the responsibility of meeting success criteria (e.g. the JavaScript **must** be made accessible).

Refer to [WAI Rich Internet Applications (WAI-ARIA)](https://www.w3.org/TR/wai-aria-1.1/) for more information.

# 3.0	URL and filename design guidelines

Queensland Government websites must comply with a set of URL design guidelines. These guidelines have been formulated to create ‘clean’ and ‘persistent’ URLs. To comply with these guidelines, an agency should use the following naming conventions for pages, sections or images:

*	Use lower case, no spaces—use hyphens to separate words (e.g. image-name-here.jpg)
*	Name the file so it clearly describes what it is (e.g. ‘red-bus.jpg’, not ‘image-563.jpg’)
*	Use keywords and follow current industry search engine optimisation guidelines
*	For images, organise the file structure based on how it will be used (e.g. consider grouping all thumbnails in a folder called 'thumbs' and name them based on the topic they represent. A feature image from the June 2013 JP mobile app could be grouped and named as follows: images/feature/201306-new-jp-mobile-web-app.jpg). 

Refer to [URL design guidelines](https://www.forgov.qld.gov.au/url-design-guidelines) for more information.

# 4.0	Structure and page types

Government franchise websites will use an information architecture (IA) similar to:
  *	‘Home page’ [Level 0] links to
  * ‘High-level audience pages’ [Level 1] links to
  *	‘Franchise landing pages’ [Level 2] links to
  *	‘Topic index pages’ [Level 3] links to
  * ‘Content pages’ [Level 4].

Things to note: 
  1.	This structure is provided for illustrative purposes only. Franchise websites can have multiple levels of index pages before attaching a content page. 
  2.	Levels 0 and 1 are controlled by OSSSIO and the Department of the Premier and Cabinet. The ‘look and feel’ and structure of these pages has already been configured based on user feedback and are unable to be modified.
  3.	All other levels can be customised to some degree. Contact OSSSIO by emailing oss.products@dsiti.qld.gov.au for assistance.  

## 4.1	Linked content

In addition to navigational linking above, franchise websites can also link to different sections within the site, to other franchises or externally, to other websites. 

### 4.1.1	Links within the franchise model 

Index pages link to other content pages or other index pages within the same franchise or other franchises (websites within www.qld.gov.au). This is necessary when content is relevant to more than one section of the IA or to more than one franchise audience. 

Ideally, links should use the same teaser text and thumbnail images as those used in the host location. The breadcrumb, section navigation and URL of the linked page should display where it is actually built in the IA. 

### 4.1.2	Links external to franchise websites 

When linking outside of the franchise, always consider the customer journey. It is better to take the customer directly to the content they are looking for rather than duplicating it or creating a page that represents an ‘extra click’ and offers little additional value.

When linking to non-Queensland Government websites give preference to credible and authoritative .gov, .edu and .org websites (e.g. peak industry associations, statutory authorities and other government or government-funded websites). Avoid links to commercial websites as these may appear to convey endorsement or affiliation

More guidelines on linking can be found in the Queensland Government [Web writing and style guide](https://www.forgov.qld.gov.au/web-writing-and-style-guide).

# 5.0	Responsive and flexible layout

Government franchise websites and online services, must use a responsive design that adjusts the layout of components for mobile devices. All layout, page and content elements must be flexible (have a fluid width) so that at lower resolutions, all 3-column layouts will compact in the correct order into 2 columns and then 1 column, based on CSS media queries.

# 6.0 Corporate identity 

The Queensland Government Single Website Experience must use the same colours, borders, shadings, imagery and/or symbols on all pages to achieve a consistent look and feel. This means that only fonts and colours specified in the approved CSS should be used. To get the CSS details or request a variation to an element, contact OSSSIO by emailing oss.products@dsiti.qld.gov.au.

# 7.0	Page models
To ensure that Queensland Government franchise websites have a consistent functionality and appearance, a set of reusable and standardised components are used to form a templated page model. This section will look at the global components that can be used on multiple pages and will also consider various components required for each specific page type.

## 7.1 Global elements

Some elements are ‘global’ because they appear across all page types (refer to the wireframe below). Other components are ‘global’ in that they can appear across multiple page types. Those elements are referenced in the component table below the wireframe. 

**Placeholder for wireframe**

**Global elements**

Ref | Component | Presence | Location (page types) | Flexibility
--- | ------------- | ------------- | ------------- | -------------
0 | Metadata and access links | Required | All  | None
1 | Header includes the Queensland Government branding/navigation bar and breadcrumb trail | Required | All  | None
2 | Global announcement (will only appear when there is a site-wide announcement such as state-wide disaster or major alert) | Required | All  | None
3 | Section navigation | Required | Topic index, standard, guide, service, 2-column, news/events index, news content  | None. Can only contain one level of navigation under the section heading
4 | Page title | Required | All*  | None. * Although each page contains a page title, it can be hidden or appear in different locations
5 | Links to child pages (IA drill-down) will display a maximum of 9 topic or content links. Each of these can then display a maximum of 4 child page (the 5th link will be ‘read more’). | Required | Franchise landing page, topic index.  | None. Order of links is based on the needs of the audience.
6 | Page options (includes ‘feedback’ button and page share options) | Optional | All  | Cannot be moved. 4 page options (Facebook, Twitter, LinkedIn and share) will be displayed. An agency can include more icons, if required.
7 | Fat footer and footer | Required | All  | None
8 | Whole-of-government notice aside (e.g. donations or important event) | Required | Can appear on any page with a right-hand panel | None. Markup, presentation and behaviour must be identical.
9 | Contact details aside (‘aside’ content always appears in the right-hand panel) If it is a ‘crisis contact’ aside, a single phone number is presented in a yellow box under the text ‘**If you are in crisis, call xxx xxx**’. This should be the first contact box on the page. | Required | Franchise landing page (optional on content pages) | None. Markup, presentation and behaviour must be identical.
10 | Aside content (e.g. related initiatives, latest news, upcoming events, contact details, tips, customer stories or case studies) As above, if it is a ‘crisis contact’ refer to component 9. | Optional | Franchise landing page, topic index, standard, guide, service, silent node, news/events index, news content. | Can be moved. Asides with different elements, locations or presentations may be possible (based on customer/business needs), but must be discussed and developed with OSSSIO ([email](oss.products@dsiti.qld.gov.au)).
11 | Main content (e.g. text, images with captions, pull-quotes, tables, embedded video) | Required | Standard, guide, silent node, 2-column, 1-column application, news content | Listed ‘content types’ are supported. If new content types are required, please contact OSSSIO ([email](oss.products@dsiti.qld.gov.au)).
12 | Page last updated date | Required | Standard, guide, silent node, news content | None
13 | Page last reviewed date | Optional | Standard, guide, silent node, news content | None
15 | Cross-selling links. These are links to journeys that are not in the section navigation on this page (e.g. could be used as a ‘related links’ section). | Optional | Standard, guide, silent node | Between 1 and 5 links are supported. Consider style guide rules when creating. 





