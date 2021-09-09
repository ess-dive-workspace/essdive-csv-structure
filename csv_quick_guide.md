# Quick Guide to the CSV Reporting Format Elements

## Contents of the Elements 

[File Structure](#file-structure)  
* [Character Set](#character-set)  
* [Delimiter](#delimiter)  
* [Data Matrix](#data-matrix)  
* [Column or Row Name Orientation](#column-or-row-name-orientation)  

[Naming Structure](#naming-structure)  
* [File Name](#file-name)  
* [Column or Row Names](#column-or-row-names)  
* [Units](#units)  

[Field Structure](#field-structure)  
* [Consistent Values](#consistent-values)  
* [Missing Value Codes](#missing-value-codes)  
* [Temporal Data](#temporal-data)  
* [Temporal Data Range](#temporal-data-range)  
* [Spatial Data](#spatial-data)  

---  

## File structure 

### Character Set  
|Element|Character Set|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement| Use the standard US-ASCII character encoding set without extensions or use UTF-8. |
|Reporting Format Description|Use the standard US-ASCII character encoding set without extensions (no characters beyond the 127 characters) or use UTF-8 (which includes the ASCII character set). Most English-language dataset submissions will require only characters included in the standard ASCII character set; however, UTF-8 is useful since it can support non-English characters. A character encoding scheme (e.g. ASCII, UTF-8) is used to map and translate bytes between computers and into human-readable characters. Using either of these character encodings will increase machine readability and interoperability.| 
|Required or Recommended | recommended |  

### Delimiter  
|Element|Delimiter|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use a comma as the delimiter while use of other commas must be protected.|
|Reporting Format Description|Save tabular data in comma separated values (CSV) format. The delimiter between columns is the comma character ",". For commas not meant to be a delimiter (e.g. used within a cell), use a vertical bar "\|" or a semicolon ";" instead of a comma or protect the comma with matching double quotation marks around the entire value.|
|Required or Recommended|strongly recommended|

### Data Matrix  
|Element|Data Matrix|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Data portion of the file organized as a matrix of rows and columns with no empty lines and equal number of columns.|
|Reporting Format Description|The contents of the data portion of the file must be organized in a logical and readable matrix format. There can be no empty rows and there must be the same number of columns across all of its rows. Dataset creators may want to consider ending CSV files with a `newline` character `\n` which indicates to any CSV reader that it has read the end of the CSV file.|
|Required or Recommended|strongly recommended|

### Column or Row Name Orientation  
|Element|Column or Row Name Orientation|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide a header Column or Row that describes the type of information found in that Column or Row.|
|Reporting Format Description|The Data Matrix portion of each file should contain a header Column or Row following the description under the "Column or Row Names" section. The Column or Row names will identify the type of information found in that Column or Row. The orientation of the header Column or Row in the Data Matrix could be presented: 1) Horizontally with names at the top of columns or 2) Vertically with names starting each row. You can describe this orientation of the data within your data matrix under Data_Orientation in the File-level Metadata templates.|
|Required or Recommended|strongly recommended|

---  

## Naming structure  

### File Name  
|Element|File Name|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use unique, descriptive file names.|
|Reporting Format Description|Provide unique file names that are as descriptive as possible about the file contents. Use only letters (e.g. CamelCase), numbers, hyphens, and underscores. Do not include spaces. Do not start with an underscore or hyphen.|
|Required or Recommended|strongly recommended|

### Column or Row Names  
|Element|Column or Row Names|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use unique, descriptive Column or Row names.|
|Reporting Format Description|Provide unique Column or Row names that convey basic information about the contents. Use only letters, numbers, hyphens, and underscores. Do not include spaces and we recommend not using CamelCase. Do not start with an underscore or hyphen and we recommend not starting with a number. Descriptions of the information found within each Column or Row should be reported and defined in the CSV Data Dictionary (CSV_dd.csv).|
|Required or Recommended|strongly recommended|

### Units  
|Element|Units|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide variable units of measurement.|
|Reporting Format Description|Provide the units of measurement for the variable in one of the following ways: 1) immediately below the Column Name as a next row or immediately adjacent to the Row Name as next column; and/or 2) only in the CSV Data Dictionary (CSV_dd.csv) Insert "N/A" when units aren't applicable. Additional information on units should be reported and defined in the CSV Data Dictionary (CSV_dd.csv). Data should be represented with units of measurement approved by the International System of Units (SI), derived units (e.g., degree Celsius). Non-SI units are accepted for use and should be defined and referenced in the CSV Data Dictionary (CSV_dd.csv). |
|Required or Recommended|required|  

---  

## Field structure  

### Consistent Values  
|Element|Consistent Values|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Be consistent within Column or Row.|
|Reporting Format Description|All data within the Column or Row must use the same units of measurement. Do not mix text and numeric data within the same Column or Row.|
|Required or Recommended|strongly recommended|

### Missing Value Codes  
|Element|Missing Value Codes|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Use consistent missing value codes.|
|Reporting Format Description|All cells in the data matrix must have a value. Cells with missing data are represented with missing value code. For Columns or Rows containing numeric data, use "-9999" as the missing value code (or modify to match significant figures given the data). For Columns or Rows containing character data, use "N/A" as the missing value code. Missing values must be represented by values that can never be construed as actual data and must be consistent across variables. Report all Missing Value Codes in the File-level Metadata whether following the reporting format guidance or using different Missing Value Codes.|
|Required or Recommended|strongly recommended|

### Temporal Data
|Element|Temporal Data|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide temporal data in UTC format or Local Standard Time with offset.|
|Reporting Format Description|A Column or Row containing temporal data can be date only following the ISO 8601 standard (YYYY-MM-DD) and completed to known precision (e.g. YYYY-MM, YYYY). Time is not required, but all times must be preceded by a date if reported in the same columns or row. If date and time are split between two columns, call one "date" and the other "time". Times must be reported in Coordinated Universal Time (UTC) (YYYY-MM-DD hh:mm:ss) (use of "Z" and "T" characters are unnecessary) or Local Standard Time reporting offset or time zone in the File-level metadata. Do not report time using Daylight Savings Time. Complete times to known precision (e.g. YYYY-MM-DD hh). For timestamped data reported as intervals, specify the interval in the column/row name or in CSV Data Dictionary (CSV_dd). Temporal data using different standards can be provided as a separate variable (i.e., in an adjacent field) but only in addition to UTC format or Local Standard Time. In cases where the entire file consists of temporal data collected at a single date and time, the date and time must be reported in the File-level Metadata.|
|Required or Recommended|recommended|

### Temporal Data Range  
|Element|Temporal Data Range|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Timestamped data presented as ranges.|
|Reporting Format Description|Present range timestamped data as paired Columns or Rows for start and stop times ("dateTime_start" and "dateTime_end" or "time_start" and "time_end").  The Column/Row Name for timestamped data given as a range should specify if the measurement is the start, stop, or midpoint value, or be explained in the CSV Data Dictionary (CSV_dd).|
|Required or Recommended|recommended|

### Spatial Data  
|Element|Spatial Data|
|:----------------------------------------------------|:----------------------------------------------------|
|Reporting Format Statement|Provide spatial data in WGS84 decimal format.|
|Reporting Format Description|All geographic coordinates must be provided in WGS84 decimal format. Latitude and longitude must be provided as separate variables (i.e., in an adjacent field). For geolocated records, each row in the data matrix must contain coordinates. Spatial data using different standards can be provided as a separate variable (i.e., in an adjacent field) but only in addition to WGS84 decimal format. In cases where the data file does not include geographic coordinates for each row/column in the data matrix and the entire file consists of measurements collected at a single location, the geographic coordinates must be reported in the File-level Metadata either as a single point location or bounding box.|
|Required or Recommended|recommended|
