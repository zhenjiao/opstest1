# Extend Build Package

OPS provides build service for convertion as well as validation, using the same build logic on local and cloud build. Here's a list of things we validate in build
1. relative links
2. file include
3. code snippet
4. metadata
5. basic markdown validation

While OPS provides basic validation during build, it may comes a need that you may want something different, to be added to it. In this case, OPS provides 3 types of customization.
1. markdown validation
2. metadata validation
3. build process customization

## Customized Markdown Validation
We support two types of validation
1. simple HTML tag validation, e.g. do not allow HTML tags like *p* or *h1* in markdown file
2. complex markdown token validation, requires user to write some plugins, e.g. do not allow writing one sentence with multiple line break

Here's an sample for simple markdown validation
[!code-json[Main](_data/markdown-validation-template.json "template of customized markdown validation")]

## Customized Metadata Validation
This feature is not yet exposed to user for customization. Once you need this feature, please [connect](../connect.md) us for feature request. 
Here's an sample which is currently used by OPS, it validates against the HTML generated from your markdown files. 
[!code-json[Main](_data/metadata-validation-template.json "template of customized metadata validation")]

## Build Process Customization
This feature is not yet exposed to user for customization. Once you need this feature, please [connect](../connect.md) us for feature request. 
