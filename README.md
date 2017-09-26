# live_nfdrs_indices

## Documentation of functionality in 'Live NFDRS Indice' Google Sheet for SLU ECC

### RAWS Auto-import sheet

A. Hourly data is imported to this sheet using 'IMPORTHTML' and 'GOOGLEFINANCE' formulas.  
(GOOGLEFINANCE is used due to its live updating, which is not possible with IMPORTHTML' formula alone)


B. There are 4 Scripts running every 15 minutes ('Update Weather') 
- All scripts are identical except for their unique url by weather station (named by station)

---
#### Example Script
function getData() {
  SpreadsheetApp.getActiveSheet().getRange('Auto-import!A2').setValue('=IMPORTHTML("http://mesowest.utah.edu/cgi-bin/droman/meso_table_mesowest_m.cgi?stn=TABC1&year1=2017&month1=9&day1=27&hour1=14&time=LOCAL&past=0"&GOOGLEFINANCE("GOOG","price"),"table",0)');
}


---

### Progress as of 9/26/2017

1. Weather records from RAWS are updated every 15 minutes automatically

2. Write script to archive(import) to 'Responses' sheet at 10:00 and 2:00 each day

3. Next step: 

  either pull hourly BI, SC, ERC data from somewhere??? Like https://cefa.dri.edu/HourlyFD/Nelson/animate/

  OR

  create formula to calculate BI with weather observations within Sheets
