# Redirection in Open Publishing

Open Publishing supports redirection at the topic level.

Write a [metadata](metadata.md) with name "redirect_url" in the yaml header, then the page will redirect to the topic or page specified.
Note that the target URL can be either absolute or relative.

For example:

1. A full/absolute URL
```
---
redirect_url: https://msdn.microsoft.com/virtualization/windowscontainers/
---
```
2. A URL after the domain
```
---
redirect_url: /virtualization/windowscontainers/
---
```
