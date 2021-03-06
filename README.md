# getting-osm-data

###[what is osm](http://maptime.io/osm-101/#0)  
"Wikipedia of maps"

So, a global dataset of anything people map  

And it's yours (and everyone's)  

More than just basemaps, a huge source of data  


###why is this exciting?
You can use it to power your apps and do cool data analysis  

Like an app that tells you the [prices of a cup of coffee in your city](http://www.macwright.org/coffeedex/index.html#/)  
  
Or you could use it to make [cool maps](http://8bitcity.com/map?New%20York).
  
  
  
  
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

All information is stored as tags of *Key-Value* pairs.
  
So a node with a name of New York City would store it with a tag like this:  
**["name":"New York City"]**


A cafe would look like this:  
![](https://cloud.githubusercontent.com/assets/5316367/8734838/a125cc48-2bda-11e5-863f-24abd0e89701.png)
  

Let's go to [OpenStreetMap](https://www.openstreetmap.org/#map=16/40.7147/-73.9599) and explore the dataset a bit.    

It's helpful to [look at standards](http://wiki.openstreetmap.org/wiki/Tags) for tagging OSM features when you are editing or querying data.    


###using osm data  

There are two ways we can work with OSM data:  
  
  1.  Download a data file and work with it locally (PostGIS or QGIS)  
  2.  Directly query the OSM dataset with the Overpass API  
  
####Downloading data  
  
*Common sources:*   
* [Planet.osm](http://wiki.openstreetmap.org/wiki/Planet.osm)- a 575 gb file of the global dataset  
* [Continent](http://download.geofabrik.de)  
* [Metro-Area](https://mapzen.com/data/metro-extracts)  
  
*Available formats:*  
* XML (native)  
* PBF (xml binary-smaller and faster)  
* GeoJSON  
* Shapefile  

####osm data tools  
* [Overpass API](http://wiki.openstreetmap.org/wiki/Overpass_API)    
* [Osm2pgsql](http://wiki.openstreetmap.org/wiki/Osm2pgsql)  
* [ogr2ogr](http://www.gdal.org/ogr2ogr.html)    

###[licensing](https://www.openstreetmap.org/copyright)  

"OpenStreetMap® is open data, licensed under the Open Data Commons Open Database License (ODbL) by the OpenStreetMap Foundation (OSMF)."

Give Attribution  
Recognize the license (link to the copyright page)  
![](https://cloud.githubusercontent.com/assets/5316367/8735579/021fc2b0-2be0-11e5-814f-f996b599e407.png)


###example

We'll use OSM data to tell us where we could grab drinks.    

We need to know:   

1.**Where we are**  
2.**Where the bars are**  
  
We'll use the [Overpass API](http://wiki.openstreetmap.org/wiki/Overpass_API) since we don't need the entire city's data.  We're just asking for a couple of nodes nearby.  


Allows you to request specific data (with a query).  
Has it's own [query language](http://wiki.openstreetmap.org/wiki/Overpass_API/Language_Guide).    
Can be used as a backend for real-time osm applications.  

**Get our location**  

  143 Roebling Street, #2, Brooklyn, NY  
  

**Get bar locations:**  

How would we query for bars near us?  

We're looking for a specific type of node.  
This tag will be helpful: 
![amenity_bar](https://cloud.githubusercontent.com/assets/5316367/8736503/0bf95a7e-2be7-11e5-858c-4545e0b6d46d.png)  
  
Since the Overpass Query Language can be confusing, let's use a tool that helps us build our query.  
  
[Overpass Turbo](http://overpass-turbo.eu/)  
  
Once we're comfortable with the language for querying, we can directly download data from the command line or through a script:  


*overpass api*  


<pre><code>wget -O osm_bars.osm "http://overpass-api.de/api/interpreter?data=[out:json][timeout:25];(node["amenity"="bar"](40.70995118412107,-73.9604287147522,40.718236246820766,-73.9545578956604););out body;>;out skel qt;"
</code></pre>





###additional resources
* [OSM- Downloading Data](http://wiki.openstreetmap.org/wiki/Downloading_data)
* [osm2pgsql-Get your osm data into PostGIS](http://wiki.openstreetmap.org/wiki/Osm2pgsql)  
* [Osmosis-helpful tool for processing osm data](http://wiki.openstreetmap.org/wiki/Osmosis)

