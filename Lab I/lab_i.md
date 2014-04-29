Lab I: Investigate KML Conversion and Structure
===============================================

Jason Roebuck
Spatial Informatics, PSU, D. Percy, 2014 April

For this exercise, I installed the latest version of QGIS (2.2) on my workstation.

After my workstation was setup with all the necessary tools, I visited the Census Bureau's TIGER site, where I downloaded the 500k scale county pologons for the entire country.

After ensuring the data was sound by viewing it in QGIS, I used an integrated tool to export the shapefile to KML format.  The resultant KML document was just over 20MB, and when zipped to KMZ was just under 5MB.

Using Sublime Text, I opened the KML document, where I found the familiar structure of a XML document with a different root element (kml), and namespace (opengis.net/kml).

The root element within the document was `Document`, which contained `Folder`--the container for the content--and `Schema`--the definition of the attributes, with their names and types.  Within the Folder, each feature was encapsulated with a `Placemark`.  Each placemark contained the geometry, symbology, and attributes for the feature, such as this for Coffee County, Alabama:

```xml
<Placemark>
	<name>Coffee</name>
	<Style><LineStyle><color>FF000000</color><width>0.737006</width></LineStyle><PolyStyle><fill>0</fill></PolyStyle></Style>
	<ExtendedData><SchemaData schemaUrl="#counties_500k">
		<SimpleData name="GEO_ID">0500000US01031</SimpleData>
		<SimpleData name="STATE">01</SimpleData>
		<SimpleData name="COUNTY">031</SimpleData>
		<SimpleData name="LSAD">County</SimpleData>
		<SimpleData name="CENSUSAREA">678.971999999999980</SimpleData>
	</SchemaData></ExtendedData>
      <Polygon><altitudeMode>relativeToGround</altitudeMode><outerBoundaryIs><LinearRing><altitudeMode>relativeToGround</altitudeMode><coordinates>-86.030441,31.618939 -86.004085,31.619067 -85.999948,31.619311 -85.980098,31.619189 -85.926702,31.618966 -85.90446,31.618775 -85.899202,31.618729 -85.878888,31.618547 -85.832214,31.61824 -85.789142,31.617964 -85.789141,31.587866 -85.78914,31.540617 -85.789308,31.490925 -85.78937,31.487561 -85.789372,31.48743 -85.790294,31.431467 -85.789837,31.385469 -85.789815,31.383145 -85.789594,31.372698 -85.789754,31.358887 -85.789785,31.356562 -85.789866,31.350574 -85.790001,31.342857 -85.789975,31.341524 -85.790064,31.337277 -85.790065,31.336908 -85.7901,31.336276 -85.790116,31.330082 -85.790327,31.323452 -85.790434,31.320267 -85.790525,31.317495 -85.791089,31.297603 -85.791167,31.29534 -85.791243,31.294184 -85.791245,31.294004 -85.791214,31.293551 -85.791218,31.293252 -85.791361,31.291777 -85.791312,31.269325 -85.791291,31.209854 -85.791402,31.196349 -85.847766,31.196369 -85.857352,31.196367 -85.857999,31.196374 -85.865347,31.196374 -85.882227,31.196339 -85.938287,31.196344 -85.949386,31.196123 -85.950142,31.196242 -85.960322,31.195962 -85.96611,31.195935 -85.999042,31.195777 -86.01306,31.195318 -86.058535,31.194082 -86.116734,31.193015 -86.116735,31.183885 -86.116736,31.182099 -86.125405,31.182057 -86.125482,31.192754 -86.141674,31.192693 -86.193476,31.192213 -86.194003,31.211362 -86.193542,31.213028 -86.193846,31.219589 -86.193714,31.243119 -86.193336,31.250169 -86.193546,31.262915 -86.193888,31.283526 -86.194631,31.327933 -86.194779,31.336812 -86.195044,31.352681 -86.195056,31.353359 -86.196091,31.410348 -86.196365,31.425431 -86.193951,31.440072 -86.193973,31.446586 -86.194724,31.52446 -86.194784,31.529949 -86.182098,31.530047 -86.156561,31.530203 -86.156768,31.537527 -86.150314,31.537601 -86.14395,31.537675 -86.144761,31.570994 -86.145895,31.617741 -86.124952,31.618044 -86.123834,31.618167 -86.094925,31.618405 -86.058021,31.618793 -86.030441,31.618939</coordinates></LinearRing></outerBoundaryIs></Polygon>
  </Placemark>
  ```