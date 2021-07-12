# Quick Guide to the CSV Reporting Format Elements

## Contents of the Elements 

[File Structure](#file-structure)  
* [Character Set](#character-set)  
* [Delimiter](#delimiter)  
* [Data Matrix](#data-matrix)  
* [Field Name Row or Column](#field-name-row-or-column)  

[Naming Structure](#naming-structure)  
* [File Name](#file-name)  
* [Field Names](#field-names)  
* [Units](#units)  

[Field Structure](#field-structure)  
* [Consistent Values](#consistent-values)  
* [Missing Value Codes](#missing-value-codes)  
* [Temporal Data](#temporal-data)  
* [Temporal Data Range](#temporal-data-range)  
* [Spatial Data](#spatial-data)  

---  

## File structure 

### Character set  
|Element|Character Set|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement| Use the standard US-ASCII character encoding set without extensions or use UTF-8. |
|Reporting Format Description|Use the standard US-ASCII character encoding set without extensions (no characters beyond the 127 characters) or use UTF-8 (which includes the ASCII character set). Most English-language dataset submissions will require only characters included in the standard ASCII character set; however, UTF-8 is useful since it can support non-English characters. A character encoding scheme (e.g. ASCII, UTF-8) is used to map and translate bytes between computers and into human-readable characters. Using either of these character encodings will increase machine readability and interoperability.| 
|Required or Recommended | recommended |  

### Delimiter  
|Element|Delimiter|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use a comma as the delimiter while use of other commas must be protected.|
|Reporting Format Description|Save tabular data in comma separated values (CSV) format. The delimiter between columns is the comma character ",". For commas not meant to be a delimiter (e.g. used within a cell), use a vertical bar "|" or a semicolon instead of a comma or protect the comma with matching double quotation marks around the entire value.|
|Required or Recommended|strongly recommended|

### Data matrix  
|Element|Data Matrix|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Data portion of the file organized as a matrix of rows and columns with no empty lines and equal number of columns.|
|Reporting Format Description|The contents of the data portion of the file must be organized in a logical and readable matrix format. There can be no empty rows and there must be the same number of columns across all of its rows.|
|Required or Recommended|strongly recommended|

### Field name row or column  
|Element|Field Name Row or Column|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide a field name as a row or column.|
|Reporting Format Description|The Data Matrix portion of each file should contain a Field Name Row or Column following the description under Field Names. The Field Names will identify the type of information found in that row or column. The orientation of the Field Name Row or Column in the Data Matrix could be presented: 1) Horizontally with Field Names at the top of columns or 2) Vertically with Field Names starting rows. Describe the orientation of the Field Name Row or Column within the data matrix of the data file in the File-level metadata.|
|Required or Recommended|strongly recommended|

---  

## Naming structure  

### File name  
|Element|File Name|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use unique, descriptive file names.|
|Reporting Format Description|Provide unique file names that are as descriptive as possible about the file contents. Use only letters (e.g. CamelCase), numbers, hyphens, and underscores "_". Do not include spaces. Do not start with an underscore or hyphen.|
|Required or Recommended|strongly recommended|

### Field names  
|Element|Field Names|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use unique, descriptive row or column names.|
|Reporting Format Description|Provide unique row or column Field Names that convey basic information about the contents. Use only letters (e.g. CamelCase), numbers, hyphens, and underscores "_". Do not include spaces. Do not start with an underscore or hyphen. Descriptions of the information found in the fields should be reported and defined in the CSV Data Dictionary (CSV_dd.csv).|
|Required or Recommended|strongly recommended|

### Units  
|Element|Units|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide variable units of measurement.|
|Reporting Format Description|Provide the units of measurement for the variable in one of the following ways: 1) immediately below the Field Name as a next row or immediately adjacent to the Field Name as next column; and/or 2) only in the CSV Data Dictionary (CSV_dd.csv) Insert "N/A" when units aren't applicable. Additional information on units should be reported and defined in the CSV Data Dictionary (CSV_dd.csv). Data should be represented with units of measurement approved by the International System of Units (SI), derived units (e.g., degree Celsius). Non-SI units are accepted for use and should be defined and referenced in the CSV Data Dictionary (CSV_dd.csv). |
|Required or Recommended|required|  

---  

## Field structure  

### Consistent values  
|Element|Consistent Values|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Be consistent within the Field Name Row or Column.|
|Reporting Format Description|Text and numeric data must not be used in the same Field Name Row or Column. All data within the Field Name Row or Column must use the same units of measurement.|
|Required or Recommended|strongly recommended|

### Missing value codes  
|Element|Missing Value Codes|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use a consistent missing value codes.|
|Reporting Format Description|All cells in the data matrix must have a value. Cells with missing data are represented with missing value code. For Field Rows or Columns containing numeric data, use "-9999" as the missing value code (or modify to match significant figures given the data). For Field Rows or Columns containing character data, use "N/A" as the missing value code. Missing values must be represented by values that can never be construed as actual data and must be consistent across variables. Report all Missing Value Codes in the File-level Metadata whether following the reporting format guidance or using different Missing Value Codes.|
|Required or Recommended|strongly recommended|

### Temporal data
|Element|Temporal Data|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide temporal data in UTC format or Local Standard Time with offset.|
|Reporting Format Description|This field can be date only following the ISO 8601 standard (YYYY-MM-DD) and completed to known precision (e.g. YYYY-MM, YYYY). Time is not required, but all times must be preceded by a date if reported in the same field. If date and time are split between two fields, call one "date" and the other "time". Times must be reported in Coordinated Universal Time (UTC) (YYYY-MM-DD hh:mm:ss) (use of "Z" and "T" characters are unnecessary) or Local Standard Time reporting offset or time zone in the File-level metadata. Do not report time using Daylight Savings Time. Complete times to known precision (e.g. YYYY-MM-DDhh). For timestamped data reported as intervals, specify the interval in the field name or in CSV Data Dictionary (CSV_dd). Temporal data using different standards can be provided as a separate variable (i.e., in an adjacent field) but only in addition to UTC format or Local Standard Time. In cases where the entire file consists of temporal data collected at a single date and time, the date and time must be reported in the File-level Metadata.|
|Required or Recommended|recommended|

### Temporal data range  
|Element|Temporal Data Range|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Timestamped data presented as ranges.|
|Reporting Format Description|Present range timestamped data as paired fields for start and stop times ("dateTime_start and dateTime_end" or "time_start and time_end").  The field name for timestamped data given as a range should specify if the measurement is the start, stop, or midpoint value, or be explained in the CSV Data Dictionary (CSV_dd).|
|Required or Recommended|recommended|

### Spatial data  
|Element|Spatial Data|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide spatial data in WGS84 decimal format.|
|Reporting Format Description|All geographic coordinates must be provided in WGS84 decimal format. Latitude and longitude must be provided as separate variables (i.e., in an adjacent field). For geolocated records, each row in the data matrix must contain coordinates. Spatial data using different standards can be provided as a separate variable (i.e., in an adjacent field) but only in addition to WGS84 decimal format. In cases where the data file does not include geographic coordinates for each row/column in the data matrix and the entire file consists of measurements collected at a single location, the geographic coordinates must be reported in the File-level metadata either as a single point location or bounding box.|
|Required or Recommended|recommended|
