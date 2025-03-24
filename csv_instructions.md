# ESS-DIVE Reporting Format for Comma-separated Values (CSV) File Structure

## Instructions

1. A tabular data file should meet the minimum criteria as defined in the Elements:  
  a. [Detailed Guide to the Elements](csv_detailed_guide.md)  
  b. [Quick guide to the Elements](csv_quick_guide.md)
2. If the data are initially saved in a different program (e.g. Excel), comply with the reporting format, convert the file to CSV, and resolve data inconsistencies and/or formatting problems.
3. Submit a companion CSV data dictionary following the [CSV_dd_instructions](https://github.com/ess-dive-workspace/essdive-file-level-metadata/tree/main/CSV_dd).
4. Within the FLMD file, the [standard](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/flmd_quick_guide.md#standard) for each CSV guidelines reporting format related file should be **ESS-DIVE CSV v1**. If submitting your dataset to ESS-DIVE, include the keyword **ESS-DIVE CSV File Formatting Guidelines Reporting Format** in the package-level metadata.

## Notes

- CSV fields common to ESS-DIVE Package Level Metadata are consistent in format structure.  
- These elements represent the ideal file for interoperable and machine-readable data. 
- Following the recommended format and structure of the CSV Reporting Format will facilitate FLMD extraction of some fields using the [File Level Metadata Extractor](https://code.ornl.gov/ngee-arctic/ess-dive-meta)

--- 

**Contents of the Elements** 

File Structure  
* Character Set  
* Delimiter  
* Data Matrix  
* Column or Row Name Orientation

Naming Structure  
* File Name  
* Column or Row Names  
* Units  

Field Structure  
* Consistent Values  
* Missing Value Codes  
* Temporal Data    
* Temporal Data Range    
* Spatial Data  
