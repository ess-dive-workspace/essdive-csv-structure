# Quick Guide to the CSV Reporting Format

## Contents 

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
- Use the [standard US-ASCII character encoding set](detailed_guide.md#character-set) without extensions or use UTF-8.

### Delimiter  
- Save tabular data in comma separated values (CSV) format.
- For commas not meant to be a delimiter (e.g., used within a cell), consider a vertical bar "|" or a semicolon ";". Otherwise, protect the comma with matching double quotation marks around the entire value.

### Data Matrix  
- The contents of the data portion of the file must be organized in a logical and readable matrix format. There can be no empty rows, and there must be the same number of columns in each of its rows.
- See column or row orientation guidance below.

### Column or Row Name Orientation  
- The Data Matrix portion (i.e., tabular data section) of each file should contain a header Column or Row following the description under the "Column or Row Names" section of this reporting format. The Column or Row names will identify the type of information found in that Column or Row.
- Tabular data can be organized:
    - **Horizontally**, meaning that data are organized in rows and there's a new name describing the data at the start of every row
    - **Vertically**, meaning that data are organized in columns and there is a new column name describing the data at the top of every column.

---  

## Naming structure  

### File Name  
- Provide file names that are as descriptive as possible about the file contents. Use only letters (e.g., snake_case), numbers, hyphens, and underscores.
- Do not include spaces. Do not start with an underscore or hyphen.

### Column or Row Names  
- Provide unique Column or Row names that convey basic information about the contents. Use only letters, numbers, hyphens, and underscores.
- Do not include spaces or start with an underscore or hyphen. Avoid starting the column or row name with a number where possible.
- We recommend snake_case and do not recommend CamelCase or starting your column or row names with a number.

### Units  
- Provide the units of measurement for the variable in one of the following ways:
    - within the `unit` term from the [File Level Metadata Reporting Format’s Data Dictionary file](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/data_dictionary_dd/term_guide.md#unit)
    - immediately below the Column Name as the next row or immediately adjacent to the Row Name as the next column
- We recommend that you include units within the unit term in the Data Dictionary file; however, units can be included within the data file if necessary.

---  

## Field structure  

### Consistent Values  
- Be consistent within a Column or Row. Do not mix text and numeric data within the same Column or Row.
- All data within the Column or Row must use the same units of measurement

### Missing Value Codes  
- Use consistent missing value codes.
- All cells in the data matrix must have a value. Cells with missing data must be represented with a missing value code.
- If you are unclear on what missing value code to use for your data, we recommend using: 
    - "-9999" as the missing value code (or modify to match significant figures given the data) for Columns or Rows containing numeric data. 
    - “N/A” as the missing value code for Columns or Rows containing character data. 
- Missing values must be represented by values that can never be construed as actual data and must be consistent across variables.


### Temporal Data
- Dates must be reported in the ISO 8601:2019 standard (YYYY-MM-DD) and completed to known precision (e.g. YYYY-MM, YYYY). 
- Times must be reported with a date in either Coordinated Universal Time (UTC) (YYYY-MM-DDThh:mm:ssZ) or Local Standard Time with the UTC offset (YYYY-MM-DDThh:mm±hh:mm). 
- It is strongly recommended not to change the UTC offset in the middle of a time series (i.e., do not switch from Standard Time to Daylight Saving Time).

### Temporal Data Range  
- Present range-timestamped data as paired Columns or Rows for start and stop times ("dateTime_start" and "dateTime_end" or "time_start" and "time_end").
- The Column/Row Names for timestamped data should specify whether the measurement is the start, stop, or midpoint value.
- Temporal data ranges must comply with the Temporal Data section guidance (above).

### Spatial Data  
- All geographic coordinates must be provided in WGS84 decimal format. 
- Latitude and longitude must be provided as separate variables (i.e., in an adjacent field). 
- Spatial data using different standards can be provided as a separate variable (i.e., in an adjacent field), but only in addition to the WGS84 decimal format. 
For more specific guidance on providing spatial data and location metadata, review the [ESS-DIVE Location Metadata reporting format](https://github.com/ess-dive-workspace/essdive-location-metadata).

