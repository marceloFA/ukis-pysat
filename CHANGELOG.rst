Changelog
=========

Added
~~~~~
something was added

Fixed
~~~~~
something was fixed

Changed
~~~~~~~
something was changed

[master]  (2020-**-**)
----------------------

Added
*****
- ``file``: read and return booleans from env #90
- ``raster``: possibility to init with 2D array #88

[0.6.3]  (2020-09-02)
----------------------

Fixed
*****
- ``file``: imported Pattern of module typing

[0.6.2]  (2020-09-02)
----------------------

Fixed
*****
- ``raster.get_valid_data_bbox()``: was using the wrong transform #84

Added
*****
- ``file``: usage of type hints #76


[0.6.1]  (2020-08-31)
----------------------

Added
*****
- ``file``: added to_ESA_date() function #80
- ``file.get_ts_from_sentinel_filename()``: possibility to choose date format
- ``raster``: added nodata value upon dataset creation with numpy arrays #82


[0.6.0]  (2020-08-28)
----------------------

Added
*****
- ``raster.Image()``: With Statement Context Manager for Image #45
- ``raster.Image()``: Alter image array #67
- ``raster.Image()``: Target align option for `warp()` #60
- ``raster.Image()``: Pass driver specific kwargs to `write_to_file()` #74

Fixed
*****
- ``data.Source()``: Fixed query metadata return for new EarthExplorer API #71
- ``raster.Image()``: Consider all image bands in `pad()` #59
- ``raster.Image()``: Memory leak caused by `__update_dataset()` #62

Changed
*******
- ``data.Metadata()``: Corrected field types #58
- ``data.MetadataCollection()``: Improved plotting of MetadataCollection to_pandas method #56
- ``data.MetadataCollection()``: Made filter method more flexible with list and fuzzy filter options #55
- ``raster.Image()``: Split `_pad_to_bbox()` into `pad()` and `_get_pad_width()`, updated `mask()` #59
- replaced os.path with Pathlib #78

Removed
*******
- ``file``: removed `pack()` and `unpack()` #57


[0.5.0]  (2020-07-03)
----------------------

Added
*****
- ``raster.Image()``: optional nodata value for writing #32

Fixed
*****
- ``file.get_ts_from_sentinel_filename()``: Return datetime.datetime objects instead of timestamp strings #42
- ``raster.Image()``: in-memory dataset could not be updated if not GTiff and other improvements #48 #52

Changed
*******
- ``raster.Image()``: renamed `mask_image()` to `mask()`
- ``raster.Image()``: update of init signature to be less confusing #41 #50
- ``raster.Image()``: in-memory dataset now always with "GTiff" driver #53


[0.4.0]  (2020-06-05)
----------------------

Added
*****
- ``raster.Image()``: expanded test_arr to test AttributeError #31
- ``raster.Image()``: optional dimorder for arr and according test #31
- ``dn2toa()`` tests and testfiles #17
- ``data.source()``: accept WKT string as AOI #26
- ``data.source()``: check if an AOI string is a file or a WKT string #26

Fixed
*****
- ``raster.Image()``: bug in ``dn2toa()`` related to wrong array shape #17

Changed
*******
- ``raster.Image()``: changed ``dn2toa(platform, metadata, wavelengths)`` to ``dn2toa(platform, mtl_file, wavelengths)`` #17
- ``raster.Image()``: ``dn2toa`` now raises an error (instead of logging a warning) if Platform is not supported.
- ``raster.Image()``: explicit dtype when writing, optional compression #32
- ``raster.Image()``: auto-update of in-memory `dataset` #35
- removed logger


[0.3.0]  (2020-05-26)
----------------------

Added
*****
- ``download.Source()``: support for local metadata queries #6

Changed
*******
- split PyPI package into subsets to not require all dependencies for every installation #16
- ``download.Source()``: removed ``traceback`` #6
- ``download.Source()``: changed ``Source(source, source_dir=None)`` to ``Source(datahub, datadir=None, datadir_substr=None)`` #6
- ``members.Datahub()``: changed ``file`` to ``File`` #6
- updated README #6 #16

[0.2.0]  (2020-05-13)
----------------------

Added
*****
- ``download.Source()``: Classes ``Metadata`` and ``MetadataCollection`` for metadata handling #13
- expanded metadata part in README #13 - requirements: pyfields
- ``download.Source()``: ``prep_aoi()`` for on the fly preparation of aoi for queries #1
- ``data.Image()``: method ``get_subset()`` to retrieve subset array and bounding box of image tile #12
- ``download.Source()``: ``query()`` accepts now aoi in forms of geojson file with varying CRS or bounding box coordinates in Lat Lon #1
- requirements: pyproj #1
- ``download.Source()``: added methods to filter and download metadata #4
- Sentinel3 test #10

Fixed
*****
- ``download.Source()``: Improved geocoding quicklooks #5
- fixed #7

Changed
*******
- renamed ``ukis_pysat.data`` to ``ukis_pysat.raster`` and ``ukis_pysat.download`` to ``ukis_pysat.data``, breaking compatibility with version 0.1.0 #18
- ``download.Source()``: Moved ``download_metadata()`` and ``filter_metadata()`` to ``Metadata`` class #13
- ``download.Source()``: Moved all metadata mapping from ``query()`` to ``construct_metadata()`` #1
- ``download.Source()``: Changed ``_construct_metadata()`` to ``construct_metadata()`` and removed static #1
- ``download.Source()``: Simplified api queries in ``query()`` #1
- ``download.Source()``: removed ``get_metadata()`` #4
- requirements: Removed matplotlib, pandas and dask optional #9

[0.1.0]  (2020-04-29)
---------------------

- first release
