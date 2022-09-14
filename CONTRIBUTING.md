**The goal of this registry is to expand access to useful data collections available on Euro Data Cube.** With that in mind, we prefer to list collections that are clearly documented, are actively supported, can be used for research or educational purposes. Collections are included at the discretion of the Euro Data Cube team, which may remove collections from the registry at any time. Data providers are responsible for maintaining and supporting the data that they share.

## How are collections added to the registry?

Each collection in this repository is described in a dedicated YAML file in [/collections](https://github.com/eurodatacube/public-collections/tree/main/collections) directory, e.g. /collections/global-land-cover.yaml
Data providers can create a new YAML file copying the structure of the most similar existing one. After committing it to the GitHub, create a pull request and Euro Data Cube team will review it and publish it in the Registry.
Note that all external additional files should be stored in a directory with exact same name as the associated YAML file. Note also that thumbnail image should have same name as the associated YAML file. Lowercase is recommended for all files names and paths.
Users are also welcome to revise existing collections, e.g. adding new usage examples , tools, etc.

### YAML file structure
```
Name:
OpenEOPID:
Description:
Documentation:
AdditionalInfoExternal:
    Title:
    Path:
Image:
EDCBrowser:
EOBrowser:
Flickr:
Explore:
Resolution:
GeographicalCoverage:
TemporalAvailability:
TemporalResolution:
UpdateFrequency:
BandInformation:
     or
BandInformation:
  Table:
      Columns:
        - Name: Name
          Title: Name
        - Name: Description
          Title: Description
        - Name: Notes
          Title: Notes
      Rows:
        - Name:
          Description:
          Notes:
Variables:
Attributes:
ProducedResults:
     or
ProducedResults:
  Table:
      Columns:
        - Name: Name
          Title: Name
        - Name: Description
          Title: Description
        - Name: Units
          Title: Units
      Rows:
        - Name:
          Description:
          Units:
Contact:
Provider:
ManagedBy:
Tags:
License:
LicenseType:
LicenseUrl:
CustomScipts:
  Title:
  URL:
Resources:
  - Group:
    EndPoint:
    Name:
    Role:
    Type:
    Notes:
    Primary:
    CollectionId:
    Database:
    Collection:
    DatasetName:
    StoreInstanceID:
    StoreTitle:
    DataID:
  - Group:
    DatasetName:
    CollectionId:
WMTS:
  - href:
    layer_id:
    dimensions:
      warnings:
Configurations:
  - href:
    rel:
    type:
    title:
  - href:
    rel:
    type:
    title:
    sentinelhub:layer_name:
    sentinelhub:mosaicking_order:
    sentinelhub:upsampling:
DocumentationLinks:
  - href:
    rel:
    type:
    title:
Extent:
  spatial:
    bbox:
  temporal:
    interval:
CubeDimensions:
  x:
    type:
    axis:
    extent:
    reference_system:
  y:
    type:
    axis:
    extent:
    reference_system:
  t:
    type:
    extent:
    step:
  bands:
    type:
    values:
sci:citation:
Summaries:
CRS:
DataAtWork:
  Tutorials:
    - Title:
      URL:
      AuthorName:
      AuthorURL:
  Tools & Applications:
    - Title:
      URL:
      AuthorName:
      AuthorURL:
  Publications:
    - Title:
      URL:
      AuthorName:
RegistryEntryAdded:
RegistryEntryLastModified:
```
### Metadata required for each collection
 Below is a description for each metadata field.
 
| Field | Type | Description & Style |
| --- | --- | --- |
| **Name** | String | Full name of the collection|
| **Description**|MD|A high-level description of the collection. Only the first 600 characters will be displayed on the homepage of the [Euro Data Cube Public Collections](https://collections.eurodatacube.com/)|
 **Documentation**| MD| A link to documentation of the collection on the data provider's website |
|**AdditionalInfoExternal**|| Additional documentation of the collection contained in a README.MD file saved in this repository|
|**AdditionalInfoExternal >> Title**|string | Additional info |
|**AdditionalInfoExternal >> Path**|Path | path to README.MD with additional info on the github repo.|
|**Image**| Path | path to thumbnail image representing the collection that is to be displayed on the homepage . Automatically sized to 200 pixels width for display |
|**EOBrowser**|string | Link to collection displayed in EO Browser |
|**Flickr**|string | Link to Flickr album if collection is not available on EO Browser |
|**Explore**|MD | Link to where the collection can be explored. E.g Jupyter notebook or graphical viewer |
|**Resolution**|MD | Spatial resolution of raster collection|
|**GeographicalCoverage**|MD| a short description on geographical coverage of the collection, it could be land, ocean, or lat-lon extents.|
|**UpdateFrequency**|MD| An explanation of how frequently the collection is updated|
|**TemporalAvailability**|MD| the time period of availability of the collection|
|**BandInformation**|MD| description of available bands and data. It could be a link to the description or a table with the description |
|**CustomScripts**|MD | Link to the collections' custom scripts |
|**Contact**|string|contact details |
|**License**|MD|An explanation of the collection license and/or a link to more information |
|**ManagedBy**|MD|The name of the organization who is responsible for the collection |
|**Provider**|MD|The name of the organization who provides the collection |
|**Tags**|List of strings|Tags that topically describe the collection. Tags must include either `open data` or `commercial data` , `xcube` or `sentinel hub` or `geodb` , `raster` or `vector` , `systematic` or `on-demand`|
|**Resources**|List of lists|A list of resources to access the collections. Each resource entry requires collection specific metadata as below:|
|**Resources > Group**|String| Category of the resources. Must either be `Sentinel Hub Resources` or `xcube Resources` or `geoDB Resources` |
|**Resources > Endpoint**|String|endpoint where the Sentinel Hub collection can be accessed. Should start with the protocol (`https://`).|
|**Resources > Type**|String|Sentinel Hub Collection identifier name e.g S1LC|
|**Resources > CollectionId**|String|Sentinel Hub BYOC collection ID|
|**Resources > Database**|String|Name of geoDB database of the collection|
|**Resources > Collection**|String|Name of geoDB table collection|
|**Resources > StoreInstanceID**|String|ID of the xcube store|
|**Resources > StoreTitle**|String|Name of xcube store of the collection|
|**Resources > DataID**|String|Name identifier of the collection in the xcube store|
|**Resources > Notes**|MD| More info concerning the collection.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications]** (Optional)|List of lists|A list of links to example tutorials, tools & applications, publications that use the data.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > Title**|String|The title of the tutorial, tool, application, or publication that uses the data.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > URL**|String|A link to the tutorial, tool, application, or publication that uses the data.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > AuthorName**|String|Name(s) of person or entity that created the tutorial, tool, application, or publication. Limit scientific publication author lists to the first six authors in the format Last Name First Initial, followed by 'et al'.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > AuthorURL**|String|(Optional) URL for person or entity that created the tutorial, tool, application, or publication.| 

### Metadata used by the EDC Browser

| Field                            | Type   | Description & Style        |
|----------------------------------|--------| --------------------------|
|||

### Metadata used within the openEO Platform project

| Field                            | Type   | Description & Style        |
|----------------------------------|--------| --------------------------|
| **OpenEOPID**                    | String | **REQUIRED.** Collection name to be used within openEO Platform, should be all caps.                             | 
| **WMTS**                         | List of dictionary | Based on [STAC Web Map Links Extension](https://github.com/stac-extensions/web-map-links)                        | 
| **WMTS > href**                  | String | Link to the WMTS, without any WMTS specific query parameters.                                                    |
| **WMTS > layer_id**              | String | The layers to show on the map.                                                                                   | 
| **WMTS > dimensions**            | String | Any additional dimension parameters to add to the request as key-value-pairs, usually added as query parameters. | 
| **WMTS > dimensions > warnings** | String | Should always be set to YES for openEO. Platform |
| **Extent** | | | |
| **CubeDimensions** | | |
| **CubeDimensions > x/y** | | |
| **CubeDimensions > x/y > type** | | |
| **CubeDimensions > x/y > axis** | | |
| **CubeDimensions > x/y > extent** | | |
| **CubeDimensions > x/y > reference_system** | | |
| **CubeDimensions > t** | | |
| **CubeDimensions > t > type** | | |
| **CubeDimensions > t > axis** | | |
| **CubeDimensions > t > extent** | | |
| **CubeDimensions > t > reference_system** | | |
| **Summaries** | Dictionary | A map of property summaries, either a set of values, a range of values |
| **CRS** | List | List of coordinate reference systems supported by the backend. |

## How to make use of these collections

Please see the usage examples provided for each individual collection.

