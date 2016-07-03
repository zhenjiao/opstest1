# Open Publishing Backlog
Our backlog is available in TFS: [All active OPS features](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems?path=Shared%20Queries%2FPM%20Queries%2FAll%20active%20OPS%20features&_a=query).

SEO feature requests are [here](https://mseng.visualstudio.com/DefaultCollection/VSChina/SEO/_backlogs#level=Features&showParents=false&_a=backlog).

# 1. Report Feature Requests, Bugs, or Live Site Incidents (LSI) ###
Work item criteria:
* **Live Site issue**
    * End point is down
    * Failures in the LIVE branch
    * [SLA](https://microsoft.sharepoint.com/teams/Visual_Studio_China/Service%20Delivery%20SD/DEVOPs/LSI-Severity-Metrix.xlsx?web=1)
* **Bug**
    * Anything failing in any branch except for LIVE. 
    * If you have not published live yet, unless the site is down, anything else is considered a bug.
* **Feature request** 
    * New functionality or change or improvement of existing functionality.

You can use MSDNHelp or TFS listed above. 

## 1.1 Using MSDNHelp
The MSDN Help Portal can be used for requests by Internal Customers, Partners, and Stakeholders via a form without the need to deal with TFS. All submissions will result in a TFS work item being created in [Open Publishing TFS](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems) and an email confirmation sent to the submitter and the person who opened the request with a link to the TFS work item. 

MSDNHelp is the preferred method to log issues as it simplifies the interface.

### 1.1.1 Opening a Live Site Issue (LSI) via the MSDNHelp portal

1. Go to [http://MSDNHelp](http://MSDNHelp).
2. Click on **Live Site Incident (LSI)**.
3. Under **Application**, select **Open Publishing**.
4. Follow the instructions in the form to fill out the fields.
5. Click on **Submit**.
	 
### 1.1.2 Opening a bug or a feature request via the MSDNHelp portal

1. Go to [http://MSDNHelp](http://MSDNHelp).
2. Click on **Platform and Tools Feature requests** link.
3. Under **Application**, select **Open Publishing**.
4. Follow the instructions in the form to fill out the fields.
5. Click on **Submit**.

Please find [this query](https://mseng.visualstudio.com/VSChina/Open%20Publishing/_workitems?path=Shared%20Queries%2FVSOpenPublishing%2FOP%20-%20Active%20bugs%20unassigned&_a=query) for all OPS bugs not yet triaged.

## 1.2 Using TFS
You can enter requests or issues directly in TFS if you choose so. Note that any item outside the listed area paths below might not be triaged. So use MSDNHelp if possible.

### 1.2.1 Opening a Live Site Incident (LSI) in TFS
This option is not available via TFS. Please enter LSIs via MSDNHelp only.
	 
### 1.2.2 Opening a bug in TFS
1. Go to [Open Publishing TFS](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems).
2. Select **New** and then **Bug**
3. For **Area Path**, choose **VSChina\OpenPublishing** or **VSChina\Open Localization** for localization bugs
3. For **Iteration**, choose **VSChina**
4. **Do not assign the item to anybody**
5. Enter your **Priority**.
6. For **Issue Type**, choose **Code defect**.
7. For Release, chosee **MSDN**.
5. Enter a description of the issue (include your repo and end-point URL).

If the bug is a blocking issue, contact [Sandra Aldana](mailto:saldana) for escalation.

### 1.2.3 Opening a feature request in TFS

1. Go to [Open Publishing TFS](https://mseng.visualstudio.com/DefaultCollection/VSChina/_workitems).
2. Select **New** and then **Feature**
3. For **Area Path**, choose **VSChina\OpenPublishing** or **VSChina\Open Localization** for localization requests
3. For **Iteration**, choose **VSChina**
4. **Do not assign the item to anybody**
5. Enter your **Priority**.
6. In the **Description** field, enter: Business Justification, Personas/Users that need the feature, as well as Experiences, without implementation details.
7. Fill the rest of the fields and submit the item