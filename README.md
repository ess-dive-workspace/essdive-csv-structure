# ESS-DIVE Reporting Format for Comma-separated Values (CSV) File Structure v1.0.1

Tabular data in the form of rows and columns should be archived in its simplest form. Submit these data following the ESS-DIVE Reporting Format for Comma-separated Values (CSV) File Structure. The CSV reporting format is more likely accessible by future systems over a proprietary format and is preferred because this format is easier to exchange between different programs increasing the interoperability of the data file. Defining the reporting format and structure of the CSV file and some field content increases the machine-readability of the data file for extracting, compiling, and comparing the data across files and systems. 
 

## Getting started

Instructions for how to use this reporting format:

- [CSV reporting format instructions](csv_instructions.md)

Other documents:

- [Detailed Guide to the Elements](csv_detailed_guide.md)
- [Quick Guide to the Elements](csv_quick_guide.md)

---
## Updates in v1.0.1 
In March 2025, a patch version of the CSV File Formatting Guidelines reporting format was made to improve the overall experience with the associated reporting format documentation. Additionally, the standard reporting format keyword and standard term were added to the csv_instructions.md file.

## How to contribute

This CSV data reporting format is evolving and growing to meet the needs of researchers. Feedback and new contributions are welcome towards the development of new versions. If you would like to suggest a change or report a problem, please submit a GitHub issue using one of the templates we provide.

If you have any questions about this reporting format, you can also directly email ESS-DIVE support at ess-dive-support@lbl.gov.

Our issue templates were based on those used by Darwin Core:

Darwin Core maintenance group, Biodiversity Information Standards (TDWG) (2014). Darwin Core. Zenodo. https://doi.org/10.5281/zenodo.592792

## Copyright information

This repository content is license for use under the [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/)

## Funding and acknowledgements  

Funding for the development of ESS-DIVE's generic comma-separated values (CSV) text format files was provided by the U.S. Department of Energy, Office of Science, Office of Biological and Environmental Research, Climate and Environmental Science Division, Data Management program under contract number DE-AC02-05CH11231.

## Recommended Citation

Velliquette, T., Welch, J., Crow, M., Devarakonda, R., Heinz, S., Crystal-Ornelas, R. (2021). ESS-DIVE Reporting Format for Comma-separated Values (CSV) File Structure. Environmental Systems Science Data Infrastructure for a Virtual Ecosystem (ESS-DIVE), ESS-DIVE Repository. https://doi.org/10.15485/1734841

## Related Reference 

McNelis, J., Crow, M., and Devarakonda, R., ESS-DIVE File Level Metadata Extractor. Computer Software. https://code.ornl.gov/ngee-arctic/ess-dive-meta. 01 Oct. 2020. Web. doi:10.11578/dc.20201103.5.  

## References  

This recommended CSV file reporting format is based on a combination of existing guidelines and recommendations including some found within Earth Science research with additional input from the Environmental Systems Science (ESS) researchers. While there are many variants, RFC 4180 (Shafranovich 2005) is commonly treated as the standard. The BADC-CSV format (Pepler & Parton 2009) is a variant of the CSV file format created by the British Atmospheric Data Centre for atmospheric observation data. Similarly, the ASCII format (Evans et al. 2016) can be considered a variant of a CSV file when the content is delimited with a comma. The ASCII format follows RFC 4180, is intuitive, and was created for Earth science data. CSV files are compatible with Unicode and ASCII character sets; however, the EDI recommends ASCII text (256 characters) delimited by tab or comma (EDI 2019).   

EDI (Environmental Data Initiative). 2019. Five phases of data publishing - Phase 2: Format and QC data tables. https://environmentaldatainitiative.org/five-phases-of-data-publishing/phase-2/

Evans, K., et al. 2016. ESDS-RFC-027v1.1 - ASCII File Format Guidelines for Earth Science Data. https://cdn.earthdata.nasa.gov/conduit/upload/4827/ESDS-RFC-027v1.1.pdf

Klyne, G. (2002) RFC 3339 - Date and Time on the Internet: Timestamps. https://tools.ietf.org/html/rfc3339

Pepler, S., Parton, G. (2009) The BADC Text File Guide for users, and producers. Documentation. https://help.ceda.ac.uk/article/105-badc-csv

Shafranovich, Y. (2005) RFC 4180 - Common Format and MIME Type for Comma-Separated Values (CSV) Files. https://tools.ietf.org/html/rfc4180
