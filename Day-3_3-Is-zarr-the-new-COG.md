
"No."
They're not comparable.

--

They aren't directly comparable.

C - cloud optimised
O - optimised
G - geo

Organise metadata read at the beginning. 
GeoMetadata is required the TIFF array format

Zarr:
Multidimensional arrays

![[Pasted image 20251119121551.png]]


Multiple arrays inside groups.
Build up hierarchy inside Zarr store
Each array group can have metadata associated with it
-> no geo by default, as it's just an array format

**Conventions**

Can put a spec out /schema for conventional way of doing Zarr

Potential conventions: 
- Geospatial project
- multi-scale and overviews

But these don't exist.

If this existed they could compare to COG.

--

**Comparing Zarr and TIFF array formats**

**Chunking**

Normally for an array they are Linearised as a step then saved.
- Linearisation

In Zarrs: chunks are just saved as they are created, it's not it's own step.
They are the unit of compression.

TIFF: only support 2-dimensional arrays
Zarr support full N-dimensional

![[Pasted image 20251119121816.png]]

**Compression**

(it's complicated)

But if Zarr is faster need to ask why, or if it even is if everything is the same.

Summary
- TIFF:
	- stable: no updates for 33 years
	- proven interoperable
	- proven portable
- ZARR:
	- n-dimensional arrays
	- more advanced (nicer) compression

**Organising**

STAC catalog

Can organise ZARR nicely in S3 -- makes it "cloud optimised".

--

Better format: CCRP
-> problems with object storage