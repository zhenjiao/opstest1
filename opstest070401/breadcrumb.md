---
author: tspowen
---
#Breadcrumb 

Breadcrumb is a very common navigation component, it usually appears at the top of the page that enables the user to navigate to higher-level document collections. Also, the breadcrumb offers users an idea about under which part of the site a user is currently viewing. In OPS, breadcrumb is a very similar concept as TOC, that the structure is specified in a separated file in a structured way, other pages just reference the breadcrumb file and render on the page. Here is a sample:
![Breadcrumb sample](../images/breadcrumbsample.png)

##What does the breadcrumb source file look like
In OPS, breadcrumb data is put into a toc.yml file. This is a YAML format file and the breadcrumb data are organized in a parent-child relationship, this relation specifies a logic navigation path for the site. For example:

```md
- name: Enterprise Mobility
  href: /EM/
  homepage: /EM/index
  items:
  - name: Solutions
    href: /EM/Solutions/
    homepage: /EM/Solutions/byod-design-considerations-guide
  - name: Advanced Threat Analytics
    href: /ATA/
    homepage: /ATA/index
    items:
      - name: Understand and explore
        href: /ATA/Understand/
        homepage: /ATA/understand/ata-understand-and-explore
      - name: Plan and design 
        href: /ATA/PlanDesign/
        homepage: /ATA/plandesign/ata-plan-and-design    
  - name: Intune
    href: /InTune/
    homepage: /InTune/index
    items:
      - name: Understand and explore
        href: /Intune/Understand/
        homepage: /Intune/understand-explore/ways-to-do-enterprise-mobility
      - name: Deploy and use
        href: /Intune/DeployUse/learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents
        homepage: 
``` 

 In the above example, there is a path of `Enterprise Mobility -> Advanced Threat Analytics -> Plan and Design`. There are also three types of input in the yaml file. **The three fields are mandatory**:
* `name` - The display text that shows up on the breadcrumb. For the parent node (in this case EM, it needs to be the location of the toc.yml file)
* `href` - This is the URL part to detect which breadcrumb node to match. 
  * **It needs to be the absolute path from the site domain, not from the Git repository**.
  * It always have to start and end with a forward slash `/`.
  * *MSDN/TN/VS.com Logic* To match and show the correct breadcrumb entry, you must have a toc file directly under the path you're referring to, so the topics referenced by that toc would have the particular breadcrumb entry highlighted.
    * Note: If you have only 1 TOC file for your entire docset, the breadcrumb won't help navigate inside your docset, but you can use it to connect multiple docsets. If you already have separated TOC files for your docset, you can use breadcrumb to connect those separated TOC together.
  * *docs.microsoft.com Logic* For example, if current open page is `http://docs.microsoft.com/ATA/Understand/samplefile.html`, then it will look up the breadcrumb source and figured out that this page is under 'ATA -> Understand'. Then the node will be highlighted. 
* `homepage` - This is a URL that leads to a landing page after user click the breadcrumb node.

##Where to put the breadcrumb source file
The breadcrumb source file (toc.yml) can be put in any folder within a provisioned docset in your repo, or in any folder in another provisioned docset in a different OP repo. That is because breadcrumb is usually a global navigation concept and links different docsets and repos. So you could put the toc.yml file under any OP provisioned docset. Note that in this case, all the repos need to publish to the same domain. 

For example, if you put the toc.yml file under the root folder of docset "EnterpriseMobility", whose base url is /EM/, after building the docset, you can verify the built breadcrumb data via `http://{SiteDomain}/EM/toc.json`.  

The only restriction is that you do not put the toc.yml file in the same folde than the TOC.md file. By doing so, the build system will pick up only the toc.yml file and the TOC.md file will not be picked. 

For example, if you want to put the toc.yml file it in a docset that already has a TOC.md in root folder, one solution is to put the toc.yml file in a subfolder, say `A`, and specify breadcrumb_path to `/{base path of the docset}/A/toc.json`.

In order to reference the breadcrumb source file, you need to update **ALL** the docfx.json files that are going to use the breadcrumb. This needs to be done as global metadata, so that current docset will pull breadcrumb data from specified location. In this case, is /EM/toc.json. Add the `breadcrumb_path` line:

```json
    "globalMetadata": {
      "layout": "Conceptual",
      "breadcrumb_path": "/EM/toc.json",
      "ms.locale": "en-us"
    }
```

##How to include breadcrumb source file for build
Additionally, we need to indicate the build system that we need to include the YAML file in the build. Thus, **ONLY** in the docset where the toc.yml file is place, update the docfx.json file. You need to add the .yml extension in the `files` section.

```json
     "content":
      [
        {
          "files": ["**/**.md", "**/**.yml"],
          "exclude": ["**/obj/**"]
        }
      ],
```

##Why the breadcrumb does not show on my page?
1. Please view your page source to check if there is a breadcrumb_path metadata in the page source. If yes, check if the path filled with expected location.
2. If there is no breadcrumb_path metadata, please check if the breadcrumb_path is added as global_metadata in docfx.json in your repo.
3. If everything above is correct, please double-check the breadcrumb source file to see if the href is set correctly.
4. Check if the breadcrumb source file has been included for build.
5. Report issue on //MSDNHelp.
