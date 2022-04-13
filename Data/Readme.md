## Dataset Used in this Project

1. Construction_Model.xlsx
1. data2021-full.csv
1. property-assessment-fy2019-data-key.pdf
1. propertyoccupancycodes.pdf

## Dataset Source
<p align="justify">PROPERTY ASSESSMENT FY2021 (2021, December 07). *Gives property, or parcel, ownership together with value information, which ensures fair assessment of Boston taxable and non-taxable property of all types and classifications.* 

URL: https://data.boston.gov/dataset/property-assessment/resource/c4b7331e-e213-45a5-adda-052e4dd31d41


## The Data API can be accessed via the following actions of the CKAN action API.

**CREATE**	        https://data.boston.gov/api/3/action/datastore_create
**UPDATE / INSERT**	https://data.boston.gov/api/3/action/datastore_upsert
**QUERY**	            https://data.boston.gov/api/3/action/datastore_search
**QUERY (VIA SQL)**	https://data.boston.gov/api/3/action/datastore_search_sql


## A simple request to the data API using Python.

<pre>
<code>
import json
import urllib.request
url = 'https://data.boston.gov/api/3/action/datastore_search?resource_id=c4b7331e-e213-45a5-adda-052e4dd31d41&limit=5&q=title:jones'  
fileobj = urllib.request.urlopen(url)
response_dict = json.loads(fileobj.read())
print(response_dict)
</code>
</pre>


## A simple ajax (JSONP) request to the data API using jQuery.

<pre>
<code>
var data = {
    resource_id: 'c4b7331e-e213-45a5-adda-052e4dd31d41', // the resource id
    limit: 5, // get 5 results
    q: 'jones' // query for 'jones'
  };
  $.ajax({
    url: 'https://data.boston.gov/api/3/action/datastore_search',
    data: data,
    dataType: 'jsonp',
    success: function(data) {
      alert('Total results found: ' + data.result.total)
    }
  });
</code>
</pre>  
