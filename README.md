# FOSS4G-2025-notes
Elena's notes from attending FOSS4G


## Workshop 1: Diving in to pygeoapi

https://dive.pygeoapi.io/

Bare metal run:
repo  https://github.com/geopython/pygeoapi/

* Create `venv`
* Must have env var that points to config YAML:
  `PYGEOAPI_CONFIG`
  eg: 
```
export PYGEOAPI_CONFIG=example-config.yml
```

Recommended copy template:

https://github.com/geopython/pygeoapi/blob/master/pygeoapi-config.yml

```
cp pygeoapi-config.yml example-config.yml
```

commands to run:
```
pygeoapi openapi generate $PYGEOAPI_CONFIG --output-file $PYGEOAPI_OPENAPI
pygeoapi serve
```
serves at:  http://localhost:5000

### PYGEOAPI_CONFIG

The config does virtually everything.

This is very sensibly organised.

The workshop exercises are reference implementations.

In `pygeoapi` features out of the box:
* dynamic pagination
* config: max records returned
* config `extents`:
  This is in the config specifically for performance reasons
	* `spatial`
	* `temporal`
* config: `properties`: can choose to return arbitrary columns/column order 
* config: `providers`
	* eg: `map` 
	* can add custom/arbitrary/byo
	  docs on ingestion: https://docs.geoconnex.us/contributing/step-2/pygeoapi/providers/
	

List: https://github.com/geopython/pygeoapi/tree/master/pygeoapi/provider

**[\*]Current list of Providers**
azure_.py
base.py
base_edr.py
base_mvt.py
csv_.py
csw_facade.py
elasticsearch_.py
erddap.py
esri.py
filesystem.py
geojson.py
hateoas.py
mapscript_.py
mongo.py
mvt_elastic.py
mvt_proxy.py
mvt_tippecanoe.py
ogr.py
oracle.py
parquet.py
postgresql.py
rasterio_.py
sensorthings.py
socrata.py
sqlite.py
tile.py
tinydb_.py
wms_facade.py
wmts_facade.py
xarray_.py
xarray_edr.py


#### Notes:

* Routes: emergent from config: `collections`, `processes`, etc, very sensible
* By default: sqlalchemy SQL connector, but doesn't really matter.
* Doesn't use Pydantic by choice: awaiting better pydantic maturity
* Copied a lot of patterns from `mapserver` as this is so longterm quiet and dependable
* Multi lingual support
* Skins


#### Currently in development:

* CRUD
* returning arbitrary formats
	* not required by OGC that a particular standard is required (per Tom both responsible for area in OGC and writing PR)

WMS server to pygeoapi
-> There is a converter
