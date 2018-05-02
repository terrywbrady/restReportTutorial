
## Demo 3: Ingest Items with Zero, One, and Two Items and apply Bitstream Filters

{% include nav.html %}

This demo will be run on demo.dspace.org.

The file [itemsWithBitstreams.zip]({{site.src_dir}}data) will be used to populate a collection used in this demonstration.

<a href="{{site.src_dir}}/data">itemsWithBitstreams.zip</a>...

You can browse the contents of this zip file [here](data/itemsWithBitstreams).

### In your test community, create a new Collection Named "Demo 3".  Ingest the __itemsWithBitstreams.zip__.

![Screenshot: Create a Collection from an Ingest Zip](batchLoadDemo3.png)

## Query for Items based on Bitstream Filters

### Open the Collection Report
![Screenshot Demo 3 Collection Report](coll3.png)
### Set the Filter based on Original Bitstream Count
This report can be used to ensure consistent bitstream content within a collection.
![Screenshot Demo 3 Filter on Bitstream Counts](coll3fBitNo.png)
![Screenshot Demo 3 Items by Bitstream Counts](coll3fBitNoRes.png)
### Set the Filter based on Original Bitstream Type (Document or Image)
This report can be used to ensure consistent bitstream content within a collection.
If this filter is paired with the metadata query tool, it can be used to enforce required metadata for a specific bitstream type.
![Screenshot Demo 3 Filter on Bitstream Type](coll3fType.png)
![Screenshot Demo 3 Items by Bitstream Type](coll3fTypeRes.png)

{% include nav.html %}
