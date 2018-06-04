## DSpace REST Reporting Tools – A REST Based Application within DSpace 6

Terry Brady

Georgetown University Library

https://github.com/terrywbrady/info

![](https://www.library.georgetown.edu/sites/default/files/library-logo.png)

---

### REST Report Tools

- Released as a part of DSpace 6
- Intended for Repository Managers
- As DSpace 6 adoption increases, it is a good time to consider these tools
- Built on the legacy DSpace 6 REST API

+++

### Purpose
- Metadata-centric view of your repository
- Check for consistency
- Generate metadata update files to repair inconsistencies
- Answer questions
- Locate feature use cases

+++

### Background

- Georgetown created a PHP of these tools for DSpace 1.8
  - Difficult to share
- Switched the code to use DSpace REST
- Contributed to DSpace 6
- Look at API landing page

+++

### Results

- No longer writing reports/queries
- Self-service reports for Digital Services team
- Self-service data exports

+++

### Try it yourself

- [Tutorial Pages](https://terrywbrady.github.io/restReportTutorial/intro)
- You can even perform this on demo.dspace.org
- Note: there are some bugs fixes that will be included in DSpace 6.3 (Jun 2018)
  - The tutorial will mention which steps depend on these fixes

---
### Setup/Test Data

The test files referenced in this presentation are available on github.

See the tutorial for instructions.

+++
## Note about the test data

The examples in this demo are contrived to make it easy to follow.

Our repository has half a million items.
We have used these tools to fix inconsistencies in thousands of item records.

---
### Create Tutorial Community

- Login as Administrator
- Create a community for the tutorial

+++
![](setup/demo3.png)
+++
![](setup/demo4.png)
+++
![](setup/demo5.png)

---
## Task 1: Metadata Consistency
+++
### Test Data
This test will use the following file to create 14 items with unique metadata.
[metadataUpload.csv](https://github.com/terrywbrady/restReportTutorial/blob/master/demo1/metadataUpload.csv)
+++
![](presentation/csv.png)
+++
### Create a Collection named Demo 1
+++
![](demo1/demo1a.png)
+++
#### Navigate to the Collection and Get Its Handle
![](demo1/demo1b.png)
+++
Edit metadataUpload.csv, replace "your-coll-handle-goes-here"
+++
![](demo1/demo1c.png)
+++
Bulk Import metadataUpload.csv
+++
![](demo1/demo1d.png)
+++
![](demo1/demo1e.png)

+++
#### Review the report and select "Apply Changes"

+++
### Demo 1 Queries
+++
Open the REST Report Query Tool:
- /rest/static/reports/query.html
+++
#### Select your "Demo 1" collection from the collection list
+++
![](demo1/q.png)
+++
#### Run the pre-defined query "Has compound subject"
- Include dc.subject in the report output
+++
![](demo1/q1.png)
+++
- Export the results and fix the metadata with a bulk update
  - Change __kitten; puppy__
  - to __kitten||puppy__

+++
![](demo1/qr1.png)
+++
#### Run the pre-defined query "Has compound dc.creator"
- Include dc.creator in the report output
+++
![](demo1/q2.png)
+++
- Export the results and fix the metadata with a bulk update
  - Change __Person Five and Person One__
    - to __Person Five||Person One__
  - Change __Person Six and Person Seven__
    - to __Person Six||Person Seven__
+++
![](demo1/qr2.png)
+++
#### Run the pre-defined query "Has URL in dc.description"
- Include dc.description in the report output
+++
![](demo1/q3.png)
+++
![](demo1/qr3.png)
+++
#### Run the pre-defined query "Has non-ascii character in metadata"
- Include dc.subject in the report output
+++
![](demo1/q4.png)
+++
![](demo1/qr4.png)
+++
#### Select "New Query" to return all items
+++
![](demo1/q5.png)
+++
- Export all results as a CSV
- Fix the lowercase titles in the export file
- Bulk update the file
+++
![](demo1/qr5.png)

---
## Queries and Filters
- Step 1 - run query, count results
- Step 2 - assemble "page" of results
- Step 3 - apply filter to page of results
  - Filter counts are scoped to 1 page
- Step 4 - add requested metadata
---
## Task 2: Filter for Unique items
DSpace will provide a listing of all withdrawn or private items, but it is difficult to see these properties in the context of other query criteria.
+++
### Demo 2: Item Special Cases - Exploring Filters
+++
Query for items containing "TODO" in dc.description.abstract
+++
![](demo2/q-todo.png)
+++
![](demo2/qr-todo.png)
+++
In DSpace, edit the item "TODO: withdraw" and Withdraw it
+++
![](demo2/withdraw.png)
+++
In DSpace, edit the item "TODO: make private" and Make it private
+++
![](demo2/private.png)
+++
Rerun the query tool, note that the withdrawn item does not appear

Items that a user cannot access will be filtered from the result set (unless you override this behavior in code)
+++
![](demo2/todoUnauth.png)
Login to the REST interface to include withdrawn items in the report
+++
- In a new tab, open /rest/static/reports/authenticate.html
- Sign in as an administrator
+++
RE-run the TODO query
+++
![](demo2/todoAuth.png)
+++
## Collection Report - Special Filters

Open the "Collection Filter" Report: /rest/static/reports/index.html
+++
![](demo2/coll.png)
+++
Set Filters to View Counts of Private and Discoverable Items
+++
![](demo2/collFilters.png)
+++
View Filter Counts
+++
![](demo2/collRes.png)
+++
![](demo2/collItems.png)
+++
Add dc.description.abstract to Item Listing
+++
![](demo2/collItemFields.png)
+++
View Item Listing with dc.description.abstract
+++
![](demo2/collItemWithFields.png)
---
## Task 3: Filter Items based on Bitstream Properties
+++
## Bitstream Properties
Ingest Items with Zero, One, and Two Items and apply Bitstream Filters

The file [itemsWithBitstreams.zip](https://github.com/terrywbrady/restReportTutorial/tree/master/demo3/data) will be used to populate a collection used in this demonstration.

+++
In your test community, create a new Collection Named "Demo 3".  Ingest the __itemsWithBitstreams.zip__.
+++
![](demo3/batchLoadDemo3.png)
+++
### Query for Items based on Bitstream Filters
+++
Open the Collection Report
![](demo3/coll3.png)
+++
Set the Filter based on Original Bitstream Count

This report can be used to ensure consistent bitstream content within a collection.
+++
![](demo3/coll3fBitNo.png)
+++
![](demo3/coll3fBitNoRes.png)
+++
Set the Filter based on Original Bitstream Type (Document or Image)

- This report can be used to ensure consistent bitstream content within a collection.
- If this filter is paired with the metadata query tool, it can be used to enforce required metadata for a specific bitstream type.
+++
![](demo3/coll3fType.png)
+++
![](demo3/coll3fTypeRes.png)
---
## Task 4: Filter Items based on Embargo Properties
+++
## Ingest Items with Embargoes

Upload a Zip file containing embargoed items into Collection "Demo 3".

The file [itemsWithEmbargoBitstreams.zip](https://github.com/terrywbrady/restReportTutorial/tree/master/demo4/data) will be used to populate a collection used in this demonstration.  

The contents file for each item sets a read restriction for the group Administrator for each item.

+++
![](demo4/embUpload.png)
+++
Set a filter to query for items with a restricted original bitstream (not visible to anonymous group)
+++
![](demo4/embFilter.png)
+++
![](demo4/embRes.png)
---
## Task 5: View Bitstream Properties

Search Collection Demo 3
+++
![](demo5/bit1.png)
+++
Add Bitstream Properties to the Result Set
+++
![](demo5/bit2.png)
+++
View Results
+++
![](demo5/bit3.png)
---
## Task 6: Custom Extensions to the the REST Query Tools

Adding Custom Queries to the Query Tool

The query tool can be easily expanded to view/enforce local metadata conventions.
+++
![](demo6/cust1.png)
+++
![](demo6/cust2.png)
+++
### Code example - Add Query

See [restQueryReport.js](https://github.com/DSpace/DSpace/blob/dspace-6.2/dspace-rest/src/main/webapp/static/reports/restQueryReport.js#L200-L246)
+++
### Code example: Add Query to the List
```
this.initQueries = function() {
  $("#predefselect")
    .append($("<option value='gu2'>GU: Has sharestream audio</option>"))
```
+++
### Code example: Set Metadata Query
```
} else if (val ==  'gu2') {
  self.drawFilterQuery("dc.relation.uri","matches","^https://mediapilot.georgetown.edu.*$");                                            
  self.drawFilterQuery("dc.type","equals","Audio");                                             
}
```
## Adding Custom Filters
+++
![](demo6/cust3.png)
+++
### Code Example: Custom Filter
```
    public class ItemFilterDefsGU implements ItemFilterList {
        public static final String CAT_GU = "GEORGETOWN Filters";
        private enum EnumItemFilterDefs implements ItemFilterTest {
            stream_auth_image("Original Bitstream with Description: Auth Image", null, CAT_GU) {
                public boolean testItem(Context context, Item item) {
                        return ItemFilterUtil.countBitstreamByDesc(BundleName.ORIGINAL, item, "Sharestream Auth Image") > 0;
                }
            },
```
+++  
### Making Results Sortable
Using code from https://kryogenix.org/code/browser/sorttable/, you can make the tables in the report tools sortable.
+++
![](demo6/cust4.png)
+++
To enable this feature, add sorttable.js to your distribution and enable the following feature in __restReport.js__
```
    //Override this method is sortable.js has been included
    this.hasSorttable = function() {
      return false;
    }
```
+++
## Enabling an Export to Google Sheets

See https://github.com/terrywbrady/PlainTextCSV_GoogleAppsScript to enable a Google Apps Script service that will create a Google Sheet from CSV.
+++
![](demo6/cust5.png)
+++
![](presentation/gsheet.png)
+++
```
    this.gsheet = function(rows) {
      var form = $("<form/>");
      $("#itemdiv").append(form);
      form.hide();
      form.attr("method","POST");
      form.attr("action","https://script.google.com/a/macros/<<your-domain>>/s/<<your-app>>/exec");
      var input = $("<textarea rows='10' cols='100'/>");
      input.attr("name","data");
      input.val(this.makeCsv(rows));
      form.append(input);
      input = $("<input type='submit'/>");
      form.append(input);
      form.submit();
    }
```
---
### Demo of Georgetown's Report Tools
(Time and Network Permitting)
---
### How might you use these tools?
---
## Thank You

Terry Brady

Georgetown University Library

https://github.com/terrywbrady/info

![](https://www.library.georgetown.edu/sites/default/files/library-logo.png)
