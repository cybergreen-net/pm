# Reference Data Package

Reference data for Cybergreen project consists of:
- Country
- ASN
- Risk

Each of reference data is used to map simple, more machine friendly expressions
with user friendly expressions, such as AS numbers to AS names, or ISO 3166-1
alpha-2 codes to country names etc... They may also include short description
or some other usefull information about data.

Reference data is used as dimensions in Cybergreen Data Warehouses

A [Data Package](http://frictionlessdata.io/guides/data-package/) is a simple
way of “packaging” up and describing data so that it can be easily shared and used.
The format is very simple, web friendly and extensible.

## set up data packages

Each reference data has it’s own repository named “referencedata-name” with
following structure:

```
├── datapackage.json
├── README.md
├── data/
│   ├── reference_data.csv
├── scripts/
│   ├── any_scripts_needed_for_extracting_or_fetching.py
├── archive/
│   ├── any_needed_original_files.txt
```
Directories `archive` and `scripts` are optional and should be created if needed.
`data` diricetory should contain actual reference data in csv fromat.

Main file for data package is `datapackage.json` - "descriptor" file in the
top-level directory of set of data files. It provides:
- General metadata such as the name of the package, path to data, fields (columns) of data etc...

Here is an example of a `datpackage.json` file:

```
"name": ref-data-example",
"title": "Reference data for example",
"resources": [{
    "name": "example",
    "path": "data/example.csv",
    "format": "csv",
    "schema": {
      "fields": [
        {
          "name": "id",
          "type": "number",
          "description": ""
        },
        {
          "name": "name",
          "type": "string",
          "description": ""
        },
        {
          "name": "date",
          "type": "date",
          "description": ""
        }
      ]
    }
  ]
}
```
