
## Demo 1: Metadata Load and Update

{% include nav.html %}

This demo will be run on demo.dspace.org.

This test will use the following file to create 14 items with unique metadata: [metadataUpload.csv](metadataUpload.csv)


### Demo 1 Setup

#### Within your test community, create a collection named "Demo1"

![Screenshot: Create Collection Demo 1](demo1a.png)

#### Navigate to the Collection and Get Its Handle

![Screenshot: Get Collection Handle](demo1b.png)

#### Edit __demo1/metadataUpload.csv__, replace "your-coll-handle-goes-here"

![Screenshot: Edit Collection Handle](demo1c.png)

#### Bulk Import __demo1/metadataUpload.csv__

![Screenshot: Select "Upload Metadata"](demo1d.png)

![Screenshot: Upload File](demo1e.png)

#### Review the report and select "Apply Changes"

### Demo 1 Queries

Open the REST Report Query Tool: https://demo.dspace.org/rest/static/reports/query.html

#### Select your "Deomo 1" collection from the collection list
![Screenshot: Select Demo 1 Collection](q.png)
#### Run the pre-defined query "Has compound subject"
- Include dc.subject in the report output
- Export the results and fix the metadata with a bulk update
  - Change `"kitten; puppy"` to `"kitten||puppy"`
![Screenshot: Subject Query](q1.png)
![Screenshot: Subject Query Results](qr1.png)

#### Run the pre-defined query "Has compound dc.creator"
- Include dc.creator in the report output
- Export the results and fix the metadata with a bulk update
  - Change `"Person Five and Person One"` to `"Person Five||Person One"`
  - Change `"Person Six and Person Seven"` to `"Person Six||Person Seven"`
![Screenshot: Creator Query](q2.png)
![Screenshot: Creator Query Results](qr2.png)
#### Run the pre-defined query "Has URL in dc.description"
- Include dc.description in the report output
![Screenshot: URL Query](q3.png)
![Screenshot: URL Query Results](qr3.png)
#### Run the pre-defined query "Has non-ascii character in metadata"
- Include dc.subject in the report output
![Screenshot: Non-ascii Query](q4.png)
![Screenshot: Non-ascii Query Results](qr4.png)
#### Select "New Query" to return all items
- Export all results as a CSV
- Fix the lowercase titles in the export file
- Bulk update the file
![Screenshot: All Query](q5.png)
![Screenshot: All Query Results](qr5.png)

{% include nav.html %}
