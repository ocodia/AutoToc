# AutoToc

Version 0.1<br />
By Paul Livingstone

AutoToc is a JavaScript tool that automatically creates a linked table of contents based on the heading tags within a web page.

## Examples
1. [Basic example](https://ocodia.github.io/AutoToc/)

## Features

* Can be scoped to any area of the page (defaults to entire body)
* Supports nested ordered and unordered lists, as well as a straight listing of links
* Auto-creates anchors for each heading (if they don't already exist)
* Supports multiple instances on one page.

## Usage

Include AutoToc:
```
<script src="AutoToc.js"></script>
```

Add a container element to contain the table of contents:
```
<ol id="toc"><ol>
```

Generate a table of contents within the container element:
```
<script>
      AutoToc("toc");
</script>
```

The container element determines the type of list that is displayed. A <code>ol</code> container will produce a nested ordered list. A <code>ul</code> container will produce a nested bulleted list. Any other container (e.g. <code>div</code>) will produce a straight list of links with no nesting. 
	

## Options

AutoToc takes three parameters:

1. Container element (string)
2. Scope (string)
3. Options (object)

```
AutoToc(containerElement, scope, options);
```

### Container element (required)

The id of the html element that you want the table of contents attached to.

### Scope (optional, default: document.body)

By default AutoToc will generate a table of contents for all headings within the body element of the web page. You can optionally restrict the scope by providing the Id attribute of a different html element within the web page.

### Options (optional)

Options allow you to change the configuration of the table of contents.

```
AutoToc("toc", "contents", { showTopLinks: true, startLevel: 2 });
```

These can be set ahead of time by changing the defaultOptions object:

```
AutoToc.defaultOptions.optionName = "optionValue";
```

The following options are available:


* **startLevel (default: 1)**: Sets the lowest heading level tag that should be included in the table.
* **depth (default: 3)**: Sets how deep the table should go.
* **showTopLinks (default: false)**: Sets if the top links should be shown.
* **topLinkToParentToc (default: false)**: Sets if the top links should link to the top of the document body or the table of contents itself.
* **topLinkClass (default: "toc-top-link")**: Sets the class of top links for styling.
* **topBodyId (default: "toc-body-top")** AutoToc will add this Id to the document body if showTopLinks = true and and an id doesn't already exist. 

