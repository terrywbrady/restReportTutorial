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

### Try it yourself

- [Tutorial Pages](https://terrywbrady.github.io/restReportTutorial/intro)
- You can even perform this on demo.dspace.org
- Note: there are some bugs fixes that will be included in DSpace 6.3 (Jun 2018)
  - The tutorial will mention which steps depend on these fixes

---
### Setup/Test Data

The test files referenced in this presentation are available on github.

See the tutorial for instructions.

---
### 1. Create Tutorial Community

- Login as Administrator
- Create a community for the tutorial

+++
![](setup/demo3.png)
+++
![](setup/demo4.png)
+++
![](setup/demo5.png)

---
### Test Data
This test will use the following file to create 14 items with unique metadata.
[metadataUpload.csv](https://github.com/terrywbrady/restReportTutorial/blob/master/demo1/metadataUpload.csv)
+++
![](presentation/csv.png)
+++

### 2. Create a Collection named Demo 1
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
  - Change
    - `"kitten; puppy"`
  - to
    - `"kitten||puppy"`
+++
![](demo1/qr1.png)
+++
#### Run the pre-defined query "Has compound dc.creator"
- Include dc.creator in the report output
+++
![](demo1/q2.png)
+++
- Export the results and fix the metadata with a bulk update
  - Change
    - `"Person Five and Person One"`
  - to
    - `"Person Five||Person One"`
  - Change
    - `"Person Six and Person Seven"`
  - to
    - `"Person Six||Person Seven"`
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
