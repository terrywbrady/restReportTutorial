## Demo 4: Ingest Items with Embargos

{% include nav.html %}

### DSpace 6.3 Code Dependency
This demo will be run on a server running an enhanced version of the report tools to address a bug in the detection of restricted bitstreams . This will be included in the DSpace 6.3 release.  It cannot yet be tested on demo.dspace.org.  It cannot yet be tested on demo.dspace.org.
* See https://jira.duraspace.org/browse/DS-3713
* See https://github.com/DSpace/DSpace/pull/1863

### Upload a Zip file containing embargoed items into Collection "Demo 3".
The file [itemsWithEmbargoBitstreams.zip](data) will be used to populate a collection used in this demonstration.  The contents file for each item sets a read restriction for the group Administrator for each item.

You can browse the contents of this zip file [here](data/itemsWithEmbargoBitstreams).

![Screenshot: Upload Zip File with Embargoed Originals](embUpload.png)

### Set a filter to query for items with a restricted original bitstream (not visible to anonymous group)

![Screenshot: Restricted Original Filter](embFilter.png)

![Screenshot: Restricted Original Filter](embRes.png)

{% include nav.html %}
