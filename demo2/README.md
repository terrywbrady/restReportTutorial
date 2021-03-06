
## Demo 2: Item Special Cases - Exploring Filters

{% include nav.html %}

This demo will be run on demo.dspace.org.

### Query for items containing "TODO" in dc.description.abstract

![Screenshot: TODO Query](q-todo.png)

![Screenshot: TODO Query](qr-todo.png)

### In DSpace, edit the item "TODO: withdraw" and Withdraw it

![Screenshot: TODO Query](withdraw.png)

### In DSpace, edit the item "TODO: make private" and Make it private

![Screenshot: TODO Query](private.png)

### Rerun the query tool, note that the withdrawn item does not appear

Items that a user cannot access will be filtered from the result set (unless you override this behavior in code)

![Screenshot: TODO Query, Unauthenticated](todoUnauth.png)

### Login to the REST interface to include withdrawn items in the report
By default, the REST Report Tools do not provide a link to a login box.  You can access a password login box at the following URL.

- In a new tab, open https://demo.dspace.org/rest/static/reports/authenticate.html
- Sign in as __dspacedemo+admin@gmail.com__

### RE-run the TODO query

![Screenshot: TODO Query, Authenticated](todoAuth.png)

## Collection Report - Special Filters

Open the "Collection Filter" Report: https://demo.dspace.org/rest/static/reports/index.html

![Screenshot: Collection Report](coll.png)

### Set Filters to View Counts of Private and Discoverable Items

![Screenshot: Collection Report Filters](collFilters.png)

### View Filter Counts

![Screenshot: Collection Report with Filters](collRes.png)

![Screenshot: Collection Report Private Items](collItems.png)

### Add dc.description.abstract to Item Listing

![Screenshot: Collection Report Private Items](collItemFields.png)

### View Item Listing with dc.description.abstract

![Screenshot: Collection Report Private Items](collItemWithFields.png)

{% include nav.html %}
