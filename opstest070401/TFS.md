# Open Publishing Backlog
Our backlog is available in TFS: [All active OPS features](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems?path=Shared%20Queries%2FPM%20Queries%2FAll%20active%20OPS%20features&_a=query).

SEO feature requests are [here](https://mseng.visualstudio.com/DefaultCollection/VSChina/SEO/_backlogs#level=Features&showParents=false&_a=backlog).

Live Site Incident List for OP is [here](https://mseng.visualstudio.com/defaultcollection/VSChina/_workitems?path=Shared%20Queries%2FVSC%20SEs%2FOPS%20LSIs&_a=query-edit).

# 1. Before logging a Live Site Incident or a Bug
> [!IMPORTANT]
> Before entering a Live Site Issue or a Bug to our team, please make sure our team has access.
> **Private** GitHub repos in Microsoft organization - Grant read-only access to "VSC-Eng-Team"
> VSO Git repos outside MSEng and DevDiv collections - Grant read-only access to "vscops@microsoft.com" and "ops@service.microsoft.com"

# 2. Report Feature Requests, Bugs, or Live Site Incidents (LSI)
You can use MSDNHelp or TFS. The MSDN Help Portal can be used for requests by Internal Customers, Partners, and Stakeholders via a form without the need to deal with TFS. All submissions will result in a TFS work item being created in [Open Publishing TFS](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems) and an email confirmation sent to the submitter and the person who opened the request with a link to the TFS work item. 

MSDNHelp is the preferred method to log issues as it simplifies the interface.

## 2.1Work item criteria:
* **Live Site issue**
    * End point is down
    * Failures in the LIVE branch
    * [See severity criteria and SLA](https://microsoft.sharepoint.com/teams/Visual_Studio_China/Service%20Delivery%20SD/DEVOPs/LSI-Severity-Metrix.xlsx?web=1)
* **Bug**
    * Anything failing in any branch except for LIVE. 
    * If you have not published live yet, unless the site is down, anything else is considered a bug.
* **Feature request** 
    * New functionality or change/improvement of existing functionality.

## 2.1 Using MSDNHelp

### 2.1.1 Opening a Live Site Issue (LSI) via the MSDNHelp portal

1. Go to [http://MSDNHelp](http://MSDNHelp).
2. Click on **Live Site Incident (LSI)** link.
3. **Live Site Issue Title** - Enter a brief and clear description of the issue.
4. **Service** - Select **Open Publishing**.
5. **Affected Area** - A link to the published content that has the issue.
6. **Issue Severity** - Select right severity. For description and examples, see [See severity criteria and SLA](https://microsoft.sharepoint.com/teams/Visual_Studio_China/Service%20Delivery%20SD/DEVOPs/LSI-Severity-Metrix.xlsx?web=1)
7. **TFS Tags** - You add tags to track your item.
8. **Description** - Enter the description of the issue as detailed as possible. Include a **link** to the repo where the content is at.
9. **Repro steps** - If applicable, add step by step instructions on how to reproduce the problem.
10. Follow the instructions in MSDNHelp if you need to attach a file.
11. Click on **Submit**.
	 
### 2.1.2 Opening a bug or a feature request via the MSDNHelp portal

1. Go to [http://MSDNHelp](http://MSDNHelp).
2. Click on **Platform and Tools Feature requests** link.
3. **Live Site Issue Title** - Enter a brief and clear description of the bug or request.
4. **Type of Request** - Select the type of request you have.
5. **Application or Service** - Select **Open Publishing** or **Open Localization**.
6. **Priority** - File the right priority as per the guidelines in the portal.
7. **TFS Tags** - You add tags to track your ticket
8. **Description** - Enter the description of the issue as detailed as possible. Include a **link** to the repo where the content is at. For bugs add a link to the repo where you content is at as well as a link to the published content.
9. **Repro steps** - For bugs, if applicable, add step by step instructions on how to reproduce the problem.
10. Follow the instructions in MSDNHelp if you need to attach a file.
11. Click on **Submit**. 

## 3.2 Using TFS
You can enter requests or issues directly in TFS if you choose so. Note that any item outside the listed area paths below might not be triaged. So use MSDNHelp if possible.

### 3.2.1 Opening a Live Site Incident (LSI) in TFS
This option is not available via TFS. Please enter LSIs via MSDNHelp only.
	 
### 3.2.2 Opening a bug in TFS
1. Go to [Open Publishing TFS](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems).
2. Select **New** and then **Bug**
3. For **Area Path**, choose **VSChina\OpenPublishing** or **VSChina\Open Localization** for localization bugs
3. For **Iteration**, choose **VSChina**
4. **Do not assign the item to anybody**
5. Enter your **Priority**.
6. For **Issue Type**, choose **Code defect**.
7. For Release, chosee **MSDN**.
5. Enter a description of the issue. Please include:
	* A link to the repo
	* A link to your published content that has the problem.

If the bug is a blocking issue, contact [Sandra Aldana](mailto:saldana) for escalation.

### 3.2.3 Opening a feature request in TFS

1. Go to [Open Publishing TFS](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems).
2. Select **New** and then **Feature**
3. For **Area Path**, choose **VSChina\OpenPublishing** or **VSChina\Open Localization** for localization requests
3. For **Iteration**, choose **VSChina**
4. **Do not assign the item to anybody**
5. Enter your **Priority**.
6. In the **Description** field, enter: 
	* Business Justification
	* Personas/Users that need the feature
	* Experiences (the what, not the how)
7. Fill the rest of the fields and submit the item
