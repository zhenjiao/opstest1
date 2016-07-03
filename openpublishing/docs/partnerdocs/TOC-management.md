# TOC creation and management #

**TOC.md** is used to define the Table of Contents (TOC) structure of a docset. The TOC is described in Markdown format.

We use Markdown headers to specify the level of the TOC. For example:
 ```markdown
# Tutorial
## Step 1
## Step 2
## Step 3
```

The above example illustrates a parent topic "Tutorial" with three children Step 1-3.

We use standard Markdown link syntax to specify the target topic of the toc node. For example:
  ```markdown
 # [Tutorial](tutorial.md)
 ## [Step 1](step-1.md)
 ## [Step 2](step-2.md)
 ## [Step 3](step-3.md)
```

If a toc node is not a link, it will become a container node: it can contain children and it will be just a expanding/collapsing node.

## Nested TOC
Some times you would like to split your giant TOC file to multiple smaller managable pieces, OPS also supports this approach. During build, we will find the TOC files referenced by the main TOC and generate a combined TOC view.

You can find 2 different syntax below, as we support either reference another TOC file, or a folder. 
 - If you include a TOC.md file, the entry you use to include the file would be rendered as a control to expand or collapse the sub TOC.
 - If you include a folder, OPS would NOT extract the toc.md in that folder, but use the 1st entry in the tocm.d file in that folder as the entry in referencer TOC.  
 ```markdown
 # [Root Index](index.md)
## [1-1 topic](1-1topic.md)
## [1-2 topic](1-2topic.md)
## [ref 2-1 toc](level-2-1/TOC.md)
## [ref 2-2 folder](level-2-2/)
```
The level of TOC entry would be the calculated a sum from the referencer and referencee TOC file for the specific entry.
> [!NOTE]
> OP doesn't support multiple level of nested TOC, so if 

## Important information ##

-  The TOC for Open Publishing is a self-contained TOC not integrated into the global MSDN/TN TOC.
-  You can use an external link to connect the Open Publishing TOC to your MSDN/TN Global TOC.
-  Since Markdown only supports 6 levels of header, we'll only support 6 levels of TOC for now. This can be extended in the future.
-  You cannot reference a file outside a docset/folder. 
- TOC.md cannot contain arbitrary Markdown content. For example, you cannot have images in it. All content that are not headers will lead to build error.

## Localized TOC ##
Localized TOC is maintained in sync with English via the handoff and handback process. TOC.md will be included in the handoff package. 

## Furthur Information ##
As OPS uses [DocFX](http://dotnet.github.io/docfx/) for transforming the content, as well as the TOC, you can find additional informatoin in this [Instruction](http://dotnet.github.io/docfx/tutorial/intro_toc.html). 
