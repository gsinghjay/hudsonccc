
![](https://web-api.textin.com/ocr_image/external/6056584bb3a4b597.jpg)

ou OmniUpdate®

OU Campus

Global XSL Reference Guide

## Global XSL

# File: breadcrumb.xsl

## Templates

Template Name:breadcrumb

Description: this template recursively goes up the file/folder structure and looks at the props files to build the breadcrumb path

### Params:

· Name: path

. Default Value: &#36;dirname

. Name: title

. Default Value: ou:pcf-param('breadcrumb')

Template Name:breadcrumb-iterate

Description: this is the template that iterates over the props files

Params:

· Name: staging-path

Default Value:

Template Name: breadcrumb-output

Description: this is the breadcrumb output template which outputs the breadcrumbs Params:

Name: staging-path

Default Value:

# File: functions.xsl

## Templates

Template Name: unparsed-include-file

Description: Grab file from production on staging and output a server side include on publish

### Params:

. Name: path

. Default Value:

Name:global

Default Value:false()

## Template Name:pcf-param

Description: Get a param from a provided parameter list

Params:

. Name: name

. Default Value:

Name: pcf-params

Default Value: &#36;pcf-params

## Functions

Function Name:ou:include-file

Description: This function takes in one parameter and outputs the proper code to include the file on the page.

## Params:

Name: fullpath

Function Name:ou:ssi

Description: this function output the server side include for the published pages,uses the variable &#36;include-type to determine the output &lt;br/&gt; supported &#36;include-type are:'php' - PHP, 'c#' - ASP/C# , 'cf' - Cold Fusion

## Params:

Name: fullpath

Function Name:ou:ssi-full

Description: function that is the full include path to a script

Params:

Name: fullpath

## Function Name: ou:pcf-param

Description: Get PCF params from an external document

Params:

. Name:name

Name: doc

Function Name: ou:pcf-param

Description: Get a param from default parameter list

Params:

. Name:name

Function Name: ou:multiedit-field

Description:get the multi edit field by label of ouc:div

Params:

Name: name

Function Name:ou:multiedit-field

Description:get the multi edit field by label of ouc:div, a pass a second parameter of a number and you will get &lt;ouc:div label="button-1"/&gt;

## Params:

Name: name

Name: position

Function Name: ou:textual-content

# Description:

OU GET TEXTUAL CONTENT

Use when checking for any content (prep for an "if empty" check)

Gets string representation of any node and its subnodes, replaces &nbsp; with space, and trims all whitespace

## Params:

Name: element

## Function Name:ou:get-tags

Description: get the individual tags for a specific page, does not include fixed tags Params:

Name: path

Function Name:ou:get-collection-children-tags

Description:get the the collection children tags

Params:

Name:collection

Function Name: ou:parent-path

# Description:

Function: ou:parent-path(&#36;path)

Used by breadcrumbs xsl. Parses a path as string and returns the path

Params:

Name: path

Function Name: ou:search-ignore-tag-start

Description: function to output the starting ignore tag for OU Search

Function Name:ou:search-ignore-tag-end

Description: function to output the ending ignore tag for OU Search

Parameters

Param Name:pcf-params

Description: save all page properties in a variable

Default Value:/document/descendant::parameter

Param Name:multiedit-fields

Description: save all multi edit fields in a variable &lt;ouc:div label="hero-image"/&gt;Default Value:/document/descendant::ouc:div[ouc:multiedit]

## Variables

Variable Name: enable-ou-search-tags

Description:variable to enable OU Search ignore tags

Default Value: false()

File: properties.xsl

Templates

Template Match:/document

Description: matching the document of the props file

Template Match:parameter[.!="]

Description: matching a parameter that is not empty

Template Match: parameter$2 r [ . = ^ { 1 1 } ]$

Description: matching a parameter that is empty

Template Match:parameter[option]

Description: matching a parameter with an option

Template Match: parameter[contains(.,'jpg')]

Description: matching a parameter with a JPG image

Template Match: @section

Description: matching section attribute of parameter

File: template-matches.xsl

Templates

Template Match: processing-instruction('pcf-stylesheet')

Description: match the pcf-sheet to make the editable region function

Template Match: ouc:*[&#36;ou:action !='edt']

Description: don't output ouc tags on publish.

Template Match:a[contains(@href,'***Broken')]

Description: Visual warning for broken dependencies tags

Template Match: processing-instruction('php')

Description: Remove closing '?' mark if not HTML5 output.

Template Match:ol[parent::ul|parent::ol]|ul[parent::ul|parent::ol]

Description: Fixes bad ul/ol nestings for pre OU Campus 10.6.2 JustEdit

Template Match: element()[@id='oualerts-archived']

Description: Match for Emergency Alerts archive div message

Modes

Mode Name:

On No Match Attribute: shallow-copy

Description:The following mode will match all items except processing instructions,copies them, then processes any children.

# File: variables.xsl

## Parameters

Param Name: ou:action

Description: Page 'state' in OU Campus(prv=Peview,Ipub=Publishedt=Edit,cmp=Compare)

Param Name: ou:uuid

Description:Unique Page ID

Param Name: ou:path

Description: Root-relative path to page output

Param Name: ou:dirname

Description: Root-relative path to current folder (USE "dirname" BELOW INSTEAD)

Param Name: ou:filename

Description:Filename of output

Param Name: ou:created

Description:Page Creation date/time

Param Name: ou:modified

Description: Last Page Modification date/time

Param Name: ou:feed

Description: Path (root-relative) to RSS Feed that's assigned to current page

Param Name: ou:servername

Description: Staging Server's Domain Name

Param Name: ou:root

Description: Path from root of staging server

Param Name: ou:site

Description: Site Name (same as foldername on staging server)

Param Name: ou:stagingpath

Description: Staging path of the file

Param Name: ou:target

Description:Name of Target Production Server

Param Name: ou:httproot

Description: Address of Target Production Server (from site settings)

Param Name: ou:ftproot

Description: Folder path to site root on Production Server (from site settings)

Param Name: ou:ftphome

Description: Initial subdirectory for site root on Production Server (from site settings)

Param Name: ou:username

Description: Active user/publisher username

Param Name: ou:lastname

Description: Active user/publisher last name

Param Name: ou:firstname

Description: Active user/publisher first name

Param Name: ou:email

Description:Active user/publisher email address

Param Name: ou:www-domain

Description:where is the main domain for multisite setup

Param Name:ou:www-ftproot

Description:where is the main ftp root for multisite setup

Param Name: ou:breadcrumb-start

Description: top level breadcrumb start position used in the breadcrumb.xsl

Param Name: ou:navigation-start

Description: standard navigation start directory variable for navigation, must start with a slash

## Variables

Variable Name:breadcrumb-start

Description:top level breadcrumb in a cleaned fashion

Default Value: if (ends-with(ou:breadcruml$b - s a r , ^ { \prime } / ) )$thenou:breadcrumb-start else concat(&#36;ou:breadcrumb-start,'/')

Variable Name: navigation-start

Description: &#36;ou:navigation-start directory variable cleaned with a slash as the end

Default Value:if (ou:navigation -start = ")thendirname else (if (ends-

with(ou:navigation-start,'/'))thenou:navigation-start else concat(&#36;ou:navigation-start,'/'))

Variable Name: nav-file

Description: navigation file for the implementation

Default Value:'_nav.inc'

Variable Name: navigation-path

Description: current navigation location for the implementation

Default Value: navigation-start I|nav-file

Variable Name: body-class

Description: Stores a body class that can be used on the HTML

Variable Name: dirname

Description: Returns the &#36;ou:dirname with a slash appended to it

Default Value: if(string-length(ou: dirname) =1)thenou:dirname else、

concat(&#36;ou:dirname,'/')

Variable Name: domain

Description: Returns the &#36;ou:httproot without a slash

Default Value: substring(ou:httproot,1,string-length(ou:httproot)-1)

Variable Name: props-file

Description: Returns the props file fiename

Default Value:'_props.pcf

Variable Name: props-path

Description: Returns the current props file path

Default Value: concat(ou:root,ou:site, dirname,props-file)

Variable Name:props-doc

Description: Returns the doc() of current props file path

Default Value: if(doc-available(props-path))thendoc(props-path) else document(")

Variable Name:page-type

Description: Returns the page type pcf param

Default Value: ou:pcf-param('page-type')

Variable Name: page-title

Description: Returns the page title from properties

Default Value:/document/ouc:properties/title

Variable Name: breadcrumb

Description: Returns the page title from properties

Default Value: ou:pcf-param('breadcrumb')

Variable Name:page-heading

Description: Returns the page heading pcf param

Default Value: ou:pcf-param('heading')

Variable Name:page-pub-path

Description: Returns the full page publish path

Default Value:domain llou:path

Variable Name: is-pub

Description: Returns true if the page is in Publish or Compare Mode

Default Value: &#36;ou:acti$i o n = ^ { \prime } p u b ^ { \prime }$

Variable Name: is-edt

Description: Returns true if the page is in Edit Mode

Default Value: &#36;ou:actio$i o n = ^ { \prime } e d ^ { \prime }$

Variable Name:is-prv

Description:Returns true if the page is in Preview Mode

Default Value: &#36;ou:actio$o n = ^ { \prime } p r v ^ { \prime }$

Variable Name: is-cmp

Description: Returns true if the page is in Compare Mode

Default Value: &#36;ou:actio$o n = ^ { \prime } c m p ^ { \prime }$

Variable Name: not-pub

Description: Returns true if the page is NOT in Publish or Compare Mode

Default Value: not(&#36;is-pub)

Variable Name: not-edt

Description: Returns true if the page is NOT in Edit Mode

Default Value: not(&#36;is-edt)

Variable Name: not-prv

Description: Returns true if the page is NOT in Preview Mode

Default Value: not(&#36;is-prv)

Variable Name:not-cmp

Description: Returns true if the page is NOT in Compare Mode

Default Value: not(&#36;is-cmp)

# File:social-meta-tag-output.xsl

Templates

Template Name:full-social-meta-tag-output

Description:template for the social meta tags output

Template Name: open-graph-tag-output

Description:facebook opengraph meta tag output

Template Name: twitter-card-tag-output

Description:twitter card meta tag output

Template Name: final-social-output

Description:template to help with social meta tag output

Params:

. Name: check-output

. Default Value:

. Name: default-output

.Default Value:

## Parameters

Param Name:enable-social-meta-tag-output

Description: xsl param to enable social meta tag output onto the pages

Default Value: false()

Param Name: ou:og-image

Description:directory variable for the og image

Param Name: ou:og-image-alt

Description: directory variable for the og image description

Param Name:ou:og-site-name

Description:directory variable for the og site name

Param Name: ou:fb-app-id

Description: directory variable for the fb app id, this is optional but when defined will give analytics back to your facebook account

Param Name:ou:og-type

Description: directory variable for declaring the type of content, as seen here https://developers.facebook.com/docs/reference/opengraph#object-type

Param Name: override-og-type

Description: override the open graph type

Param Name: override-og-image

Description: override the open graph image

Param Name: override-og-description

Description: override the open graph description

Param Name: override-og-image-alt

Description:override the og image alt

Param Name: ou:twitter-creator

Description: the twitter handle of who created the content for the twitter card

Param Name: ou:twitter-site

Description: the site of the content for the twitter card

Param Name: ou:twitter-card-image

Description: the image of the content for the twitter card, needs to be less than 5 mb

Param Name: ou:twitter-card-image-alt

Description:the image description for the twitter card, needs to be less than 420characters

Param Name:ou:twitter-card-type

Description: twitter card type, options are summary or summary_large_image

Param Name: override-twitter-card-description

Description: override the twitter card description

Param Name:override-twitter-card-image

Description: override the twitter image

Param Name: override-twitter-card-image-alt

Description:override the twitter image alt

Param Name: override-twitter-card-type

Description: override the card type options: summary or summary_large_image

Default Value: 'summary_large_image'

## Variables

Variable Name: final-og-type

Description: the final open graph type

Variable Name:final-og-image

Description:the final open graph image

Variable Name:final-og-description

Description: the final open graph description

Variable Name: final-og-image-alt

Description: the final open graph image

Variable Name: final-twitter-card-description

Description: the final twitter card description, needs to be less than 200 characters

Variable Name:final-twitter-card-image

Description: the final twitter image

Variable Name:final-twitter-card-image-alt

Description: the final twitter image alt

Variable Name: final-twitter-card-type

Description: the final twitter card type ## File: standard-outputs.xsl

Templates

Template Name: pcf-meta-data-output

Description: copy meta tags from pcf, but only those with content

Template Name: direct-edit

Description: direct edit default output

Template Name:direct-edit-script

Description: template that handles the direct edit script

Template Name:page-directive

Description: handles the output page directive for c# pages

Template Name: output-include

Description: template that handles the include statements, has conditionals for from production and condition of when it should output

### Params:

. Name: path

. Default Value:

. Name:from-prod

. Default Value: false()

. Name: global

. Default Value: false()

. Name: condition

Default Value:true(

## Template Name: output-navigation

Description:template that handles the navigation output, has conditionals for from production and condition of when it should output, also has a message option for displaying a message in preview and edit

## Params:

Name: kind

Default Value:'xsl'

Name:final-navigation-path

· Default Value: &#36;navigation-path

. Name:script-loc

. Default Value:"

. Name: global

. Default Value:false()

. Name: message

Default Value:"

. Name: debug

Default Value:false()



