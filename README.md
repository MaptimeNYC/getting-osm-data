# getting-osm-data

###[what is osm](http://maptime.io/osm-101/#0)  
"Wikipedia of maps"

So, a global dataset of anything people map  

And it's yours (and everyone's)  

More than just basemaps, a huge source of data  


###why is this exciting?
You can use it to power your apps and do cool data analysis  

Like an app that tells you the [prices of a cup of coffee in your city](http://www.macwright.org/coffeedex/index.html#/)  

To start using OSM data, we need to know  

1. **What's in the dataset**  

2. **How to access it**  

###OSM data  
######what's inside OSM?  
[The Elements](http://wiki.openstreetmap.org/wiki/Elements) of OSM data:  


* [Nodes](http://wiki.openstreetmap.org/wiki/Elements#Node)  
* [Ways](http://wiki.openstreetmap.org/wiki/Way)  
* [Relationships](http://wiki.openstreetmap.org/wiki/Relation)



Each node, way, or relation has information stored about it.  

All information is stored as tags of Key-Value pairs.


A cafe would look like this:  
INSERT keyvalues.png  
  

It's helpful to [look at standards](http://wiki.openstreetmap.org/wiki/Tags) for tagging OSM features.  


######formats  
XML (native) 
PBF  
GeoJSON  
Shapefile  

######scale
[Planet.osm](http://wiki.openstreetmap.org/wiki/Planet.osm)- a 575 gb file of the global dataset  
[Continent](http://download.geofabrik.de)  
[Metro-Area](https://mapzen.com/data/metro-extracts)  


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

1.**Where we are** 
2.**Where the bars are**

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

