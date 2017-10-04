# Tutorial for the DSpace REST Report Tools

## Report Tool Introduction
- Query Tools Features
  - Search for Audio (or course videos)
  - Filter for Audio with other assets
  - Extract with subject terms
- Collection Report Features
  - Find items with zero, one, and two bitstreams
  - Find items with an image and a document
- Normalize Thesis type
  - Update metadata to normalize
  - Use CSV/excel/metadata update

## Try it on demo.dspace.org

### Metadata Load and Update

This demo will be run on demo.dspace.org.

- Create collection
- Add spreadsheet of items
- Query for irregularities
  - Pre-defined queries
  - Construct custom query
- Bulk update to normalize

### Item Special Cases 

This demo will be run on demo.dspace.org.

- Mark item private
- Withdraw item 
- Restrict items
- Collection report - apply filters
- Login
- Collection report - apply filters

### Ingest Items with Zero, One, and Two Items (PDF and Docs)

This demo will be run on demo.dspace.org.

- Create collection
- Ingest Zips
- Run collection report to query for one, two, and three items
- Query for docs and images

### Ingest Items with Embargoe

This demo will be run on demo.dspace.org.

- Create collection
- Ingest Zips
- Run collection report to query for embargo items

### DSpace 6.x? Report Enhancements - View Bitstream Properties

This demo will be run on a server running an enhanced version of the report tools that extract bitstream properties. See PR xxx to replicate.

- Create collection
- Ingest Zips
- Run collection report to query for one, two, and three items
- Show report with bitstream properties

### Highlight Custom Extensions to the the REST Query Tools 

This demo will feature custom extensions at Georgetown.

- Pre-set queries
- Code examples
- Pre-set filters
- Code examples
- Google sheet extensions

## Files

- metadataLoad.csv
- itemsWithBitstreams.zip
  - item1-noBits
    - metadata
  - item2-oneDoc
    - metadata
    - contents
    - doc1.pdf
  - item3-twoDoc
    - metadata
    - contents
    - doc1.pdf
    - doc2.pdf
  - item4-oneImage
    - metadata
    - contents
    - image1.jpg
  - item5-twoImage
    - metadata
    - contents
    - image1.jpg
    - image2.jpg
  - item6-mixedContent
    - metadata
    - contents
    - doc1.pdf
    - image2.pdf
  - itemsWithEmbargo.zip
    - item7-embargo1
    - item7-embargo2
