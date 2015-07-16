# getting-osm-data

###[what is osm](http://maptime.io/osm-101/#0)  
"wikipedia of maps"

so, a global dataset of anything people map  

And it's yours (and everyone's)  

more than just basemaps, a huge source of data  


###why is this exciting?
You can use it to power your apps and do cool data analysis  

Like an app that tells you the [cheapest cup of coffee in your city](http://www.macwright.org/coffeedex/index.html#/)  

To using OSM data, we need to know what's actually in the data & how to access it  

###OSM data  
######what's inside OSM?  
######formats  
XML (native) 
PBF  
GeoJSON  
Shapefile  

######scale
Planet  
Continent  
Metro-Area  


###osm data sources  
###licensing  

"OpenStreetMap® is open data, licensed under the Open Data Commons Open Database License (ODbL) by the OpenStreetMap Foundation (OSMF)."

Give Attribution  
Recognize the license (link to the copyright page)  

###osm data tools  
[Overpass API](http://wiki.openstreetmap.org/wiki/Overpass_API)
<!--- "The Overpass API (or OSM3S) is a read-only API that serves up custom selected parts of the OSM map data. It acts as a database over the web: the client sends a query to the API and gets back the data set that corresponds to the query." -->
Allows you to request specific data (with a query).  
Has it's own [query language](http://wiki.openstreetmap.org/wiki/Overpass_API/Language_Guide).    
Can be used as a backend for live-osm applications.  
Cannot query historical data.  

###example

Getting OSM data to tell us where there are close places to grab drinks after Maptime.

All we need to know is:  

1.Our Location  
2.Location of bars  

Get our location  

CartoDB Office:  
143 Roebling Street, #2, Brooklyn, NY  
OSM node ID #2839628042  
  

Get bar locations:

overpass api  
<pre><code>wget -O maptime.bars.osm "http://overpass-api.de/api/interpreter?data=node(40.712327,-73.959045,40.715840,-73.955360)[amenity=\"pub\"];out;"
</code></pre>





###resources
* [OSM- Downloading Data](http://wiki.openstreetmap.org/wiki/Downloading_data)
* [Test your overpass query](http://overpass-turbo.eu/)
* []()

######data
* []()
* []()
