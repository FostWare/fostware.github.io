# Quick Reference

Below are examples of all available structural elements that can be used in a kramdown text. Since
the kramdown syntax is a superset of the Markdown syntax, only a small part of the available syntax
is not available in standard Markdown syntax. Note, that only the most basic syntax information is
given. However, a link to the detailed syntax for each element is provided (which also details the
differences to the standard Markdown syntax). The quick reference is for version **<%=
::Kramdown::VERSION %>** of the syntax documentation.

kramdown has two main classes of elements: block and span-level elements. Block-level elements are
used to create paragraphs, headers, lists and so on whereas span-level elements are used to markup
text phrases as emphasized, as a link and so on.

All examples below feature the kramdown source, the converted HTML source (shown when hovering over
the kramdown source) and the output as it appears in the browser. This looks like this:

<table class="kdexample">
<tr>
<td><pre class="kdexample-before"><code>kramdown example code</code></pre></td>
<td><pre class="kdexample-after-source"><code>Example code converted to HTML</code></pre>
<div class="kdexample-after-live" style="clear:none">
Live browser view of example code
</div>
</td>
</tr>
</table>

---
layout: default
---

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

* This is an unordered list following a header.
* This is an unordered list following a header.
* This is an unordered list following a header.

##### Header 5

1. This is an ordered list following a header.
2. This is an ordered list following a header.
3. This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

* Item foo
* Item bar
* Item baz
* Item zip

### And an ordered list:

1. Item one
1. Item two
1. Item three
1. Item four

### And a nested list:

-level 1 item
  -level 2 item
  -level 2 item
    -level 3 item
    -level 3 item
-level 1 item
  -level 2 item
  -level 2 item
  -level 2 item
-level 1 item
  -level 2 item
  -level 2 item
-level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)

### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```

# Block-level Elements - Main Structural Elements

## Paragraphs

{kdlink: {oid: paragraphs, part: "paragraphs"}}

Consecutive lines of text are considered to be one paragraph. As with other block level elements you
have to add a blank line to separate it from the following block-level element:

{kdexample::}
The first paragraph.

Another paragraph
{kdexample}

Explicit line breaks in a paragraph can be made by using two spaces or two backslashes at the end of a line:

{kdexample::}
This is a paragraph  
which contains a hard line break.
{kdexample}

## Headers

{kdlink: {oid: headers, part: "headers"}}

kramdown supports Setext style headers and atx style headers. A header must always be preceded by a
blank line except at the beginning of the document:

{kdexample::}
First level header
==================

Second level header
-------------------
{kdexample}

{kdexample::}
# H1 header

## H2 header

### H3 header

#### H4 header

##### H5 header

###### H6 header
{kdexample}

If you set the option `auto_ids` to `false` (for example, by using the `options` extension, see
[Extensions](#extensions)), then the automatic header ID generation is turned off:

{kdexample::}
{::options auto_ids="false" /}

# A header without an ID
{kdexample}

## Blockquotes

{kdlink: {oid: blockquotes, part: "blockquotes"}}

A blockquote is started using the `>` marker followed by an optional space; all following lines that
are also started with the blockquote marker belong to the blockquote. You can use any block-level
elements inside a blockquote:

{kdexample::}
> A sample blockquote.
>
> >Nested blockquotes are
> >also possible.
>
> ## Headers work too
> This is the outer quote again.
{kdexample}

You may also be lazy with the `>` markers as long as there is no blank line:

{kdexample::}
> This is a blockquote
continued on this
and this line.

But this is a separate paragraph.
{kdexample}

## Code Blocks

{kdlink: {oid: code-blocks, part: "code blocks"}}

kramdown supports two different code block styles. One uses lines indented with either four spaces
or one tab whereas the other uses lines with tilde characters as delimiters -- therefore the content
does not need to be indented:

{kdexample::}
    This is a sample code block.

    Continued here.
{kdexample}

{kdexample::}
~~~~~~
This is also a code block.
~~~
Ending lines must have at least as
many tildes as the starting line.
~~~~~~~~~~~~
{kdexample}

The following is a code block with a language specified:

{kdexample::}
~~~ ruby
def what?
  42
end
~~~
{kdexample}

## Horizontal Rules

{kdlink: {oid: horizontal-rules, part: "horizontal rules"}}

It is easy to insert a horizontal rule in kramdown: just use three or more asterisks, dashes or
underscores, optionally separated by spaces or tabs, on an otherwise blank line:

{kdexample::}
* * *

\---

  _  _  _  _

---------------
{kdexample}

## Lists

{kdlink: {oid: lists, part: "lists"}}

kramdown supports ordered and unordered lists. Ordered lists are started by using a number followed
by a period, a space and then the list item text. The content of a list item consists of block-level
elements. All lines which have the same indent as the text of the line with the list marker belong
to the list item:

{kdexample::}
1. This is a list item
2. And another item
2. And the third one
   with additional text
{kdexample}

As with block quotes, you may be lazy when using the list item marker:

{kdexample::}
* A list item
with additional text
{kdexample}

As the content consists of block-level elements you can do things like the following:

{kdexample::}
1. This is a list item

    > with a blockquote

    # And a header

2. Followed by another item
{kdexample}

Nested lists are also easy to create:

{kdexample::}
1.Item one
   1.sub item one
   2.sub item two
   3.sub item three
2. Item two
{kdexample}

Lists can occur directly after other block-level elements, however, there has to be at least one
blank line if you want to follow a paragraph with a list:

{kdexample::}
This is a paragraph.
1.This is NOT a list.

1.This is a list!
{kdexample}

Unordered lists are started by using an asterisk, a dash or a plus sign (they can be mixed) and a
space. Apart from that unordered lists follow the same rules as ordered lists:

{kdexample::}
*Item one
+Item two
-Item three
{kdexample}

## Definition Lists

{kdlink: {oid: definition-lists, part: "definition lists"}}

A definition list works similar to a normal list and is used to associate definitions with terms.
Definition lists are started when a normal paragraph is followed by a line starting with a colon and
then the definition text. One term can have many definitions and multiple terms can have the same
definition. Each line of the preceding paragraph is assumed to contain one term, for example:

{kdexample::}
term
: definition
: another definition

another term
and another term
: and a definition for the term
{kdexample}

If you insert a blank line before a definition (note: there must only be one blank line between the
terms and the first definition), the definition will be wrapped in a paragraph:

{kdexample::}
term

: definition
: definition
{kdexample}

Each term can be styled using span-level elements and each definition is parsed as block-level
elements, i.e. you can use any block-level in a definition. Just use the same indent for the lines
following the definition line:

{kdexample::}
This *is* a term

: This will be a para

  > a blockquote

#A header
{kdexample}

## Tables

{kdlink: {oid: tables, part: "tables"}}

kramdown supports a syntax for creating simple tables. A line starting with a pipe character (`|`)
starts a table row. However, if the pipe characters is immediately followed by a dash (`-`), a
separator line is created. Separator lines are used to split the table header from the table body
(and optionally align the table columns) and to split the table body into multiple parts. If the
pipe character is followed by an equal sign (`=`), the tables rows below it are part of the table
footer.

{kdexample::}
| A simple | table |
| with multiple | lines|
{kdexample}

{kdexample::}
| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}
{kdexample}

## HTML elements

{kdlink: {oid: html-blocks, part: "HTML blocks"}}

kramdown allows you to use block-level HTML tags (`div`, `p`, `pre`, ...) to markup whole blocks of
text -- just start a line with a block-level HTML tag. kramdown syntax is normally not processed
inside an HTML tag but this can be changed with the `parse_block_html` option. If this options is
set to `true`, then the content of a block-level HTML tag is parsed by kramdown either as block
level or span-level text, depending on the tag:

{kdexample::}
<div style="float: right">
Something that stays right and is not wrapped in a para.
</div>

{::options parse_block_html="true" /}

<div>
This is wrapped in a para.
</div>
<p>
This can contain only *span* level elements.
</p>
{kdexample}

## Block Attributes

{kdlink: {oid: block-ials, part: "block IALs"}}
{kdlink: {oid: attribute-list-definitions, part: "ALDs"}}

You can assign any attribute to a block-level element. Just directly follow the block with a *block
inline attribute list* (or short: block IAL). A block IAL consists of a left curly brace, followed
by a colon, the attribute definitions and a right curly brace. Here is a simple example which sets the
`title` attribute of a block quote:

{kdexample::}
> A nice blockquote
{: title="Blockquote title"}
{kdexample}

As one often wants to set one or more CSS classes on an element, there is an easy shortcut:

{kdexample::}
> A nice blockquote
{: .class1 .class2}
{kdexample}

A shortcut for setting the ID is also provided. Just prefix the ID with a hash symbol:

{kdexample::}
> A nice blockquote
{: #with-an-id}
{kdexample}

Sometimes one wants to use the same attributes for many elements. kramdown allows you to define the
attributes in one place with an *attribute list definition* (or short: ALD) and just reference this
definition in a block IAL. An ALD has the same structure as a block IAL but the colon has to be
replace with a colon, the reference name and another colon. By just using the reference name as-is
in a block IAL, one can include the attributes of the referenced ALD:

{kdexample::}
{:refdef: .c1 #id .c2 title="title"}
paragraph
{: refdef}
{kdexample}

The order in a block IAL or ALD is important because later defined attributes overwrite (with the
exception of the shortcut for CSS classes) prior defined attributes:

{kdexample::}
{:refdef: .c1 #id .c2 title="title"}
paragraph
{: refdef .c3 title="t" #para}
{kdexample}

## Extensions

{kdlink: {oid: extensions, part: "extensions"}}

kramdown provides some less used functionality through a common syntax. This will allow the easy
addition of other extensions if need arises. Currently, there are extensions for ignoring text (i.e.
treating text as comment), for inserting arbitrary text as-is into the output and for setting
kramdown options.

Here is an example that shows how to insert comments into text:

{kdexample::}
This is a paragraph
{::comment}
This is a comment which is
completely ignored.
{:/comment}
... paragraph continues here.

Extensions can also be used
inline {::nomarkdown}**see**{:/}!
{kdexample}

As one can see from the above example, the syntax for extensions is nearly identical to that of
ALDs. However, there is no trailing colon after the extension name and the extension end tag needs a
slash between the colon and the extension name. One can also use the short form of the end tag, i.e.
`{:/}`. Attribute definitions can be specified on the start tag by separating them with a space from
the extension name. Also, if the extension does not have a body, there needs to be a slash right
before the closing brace:

{kdexample::}
{::options auto_ids="false" /}

# Header without id
{kdexample}

# Span-Level Elements - Text Modifiers

## Emphasis

{kdlink: {oid: emphasis, part: "emphasis"}}

Emphasis can be added to text by surrounding the text with either asterisks or underscores:

{kdexample::}
This is *emphasized*,
_this_ too!
{kdexample}

Strong emphasis can be done by doubling the delimiters:

{kdexample::}
This is **strong**,
__this__ too!
{kdexample}

The form with the asterisks can also be used to markup parts of words:

{kdexample::}
This w**ork**s as expected!
{kdexample}

## Links and Images

{kdlink: {oid: links-and-images, part: "links and images"}}

A simple link can be created by surrounding the text with square brackets and the link URL with
parentheses:

{kdexample::}
A [link](http://kramdown.gettalong.org)
to the kramdown homepage.
{kdexample}

You can also add title information to the link:

{kdexample::}
A [link](http://kramdown.gettalong.org "hp")
to the homepage.
{kdexample}

There is another way to create links which does not interrupt the text flow. The URL and title are
defined using a reference name and this reference name is then used in square brackets instead of
the link URL:

{kdexample::}
A [link][kramdown hp]
to the homepage.

[kramdown hp]: http://kramdown.gettalong.org "hp"
{kdexample}

If the link text itself is the reference name, the second set of square brackets can be omitted:

{kdexample::}
A link to the [kramdown hp].

[kramdown hp]: http://kramdown.gettalong.org "hp"
{kdexample}

Images can be created in a similar way: just use an exclamation mark before the square brackets. The
link text will become the alternative text of the image and the link URL specifies the image source:

{kdexample::}
An image: ![gras](img/image.jpg)
{kdexample}

## Inline Code

{kdlink: {oid: code-spans, part: "code spans"}}

Text phrases can be easily marked up as code by surrounding them with backticks:

{kdexample::}
Use `Kramdown::Document.new(text).to_html`
to convert the `text` in kramdown
syntax to HTML.
{kdexample}

If you want to use literal backticks in your code, just use two or more backticks as delimiters. The
space right after the beginning delimiter and the one right before the closing delimiter are ignore:

{kdexample::}
Use backticks to markup code,
e.g. `` `code` ``.
{kdexample}

## Footnotes

{kdlink: {oid: footnotes, part: "footnotes"}}

Footnotes can easily be used in kramdown. Just set a footnote marker (consists of square brackets
with a caret and the footnote name inside) in the text and somewhere else the footnote definition (which
basically looks like a reference link definition):

{kdexample::}
This is a text with a
footnote[^1].

[^1]: And here is the definition.
{kdexample}

The footnote definition can contain any block-level element, all lines following a footnote
definition indented with four spaces or one tab belong to the definition:

{kdexample::}
This is a text with a
footnote[^2].

[^2]:
    And here is the definition.

> With a quote!
{kdexample}

As can be seen above the footnote name is only used for the anchors and the numbering is done
automatically in document order.  Repeated footnote markers will link to the same footnote
definition.

## Abbreviations

{kdlink: {oid: abbreviations, part: "abbreviations"}}

Abbreviations will work out of the box once you add an abbreviation definition. So you can just
write the text and add the definitions later on.

{kdexample::}
This is an HTML
example.

*[HTML]: Hyper Text Markup Language
{kdexample}

## HTML Elements

{kdlink: {oid: html-spans, part: "HTML spans"}}

HTML is not only supported on the block-level but also on the span-level:

{kdexample::}
This is <span style="color: red">written in
red</span>.
{kdexample}

## Inline Attributes

{kdlink: {oid: span-ials, part: "span IALs"}}

As with a block-level element you can assign any attribute to a span-level elements using a *span
inline attribute list* (or short: span IAL). A span IAL has the same syntax as a block IAL and must
immediately follow the span-level element:

{kdexample::}
This is *red*{: style="color: red"}.
{kdexample}