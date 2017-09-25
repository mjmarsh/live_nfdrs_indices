# live_nfdrs_indices

## Documentation of functionality in 'Live NFDRS Indice' Google Sheet for SLU ECC

### RAWS Auto-import sheet

A. Hourly data is imported to this sheet using 'IMPORTHTML' and 'GOOGLEFINANCE' formulas.  
(GOOGLEFINANCE is used due to its live updating, which is not possible with IMPORTHTML' formula alone)


B. There are 4 Scripts running every 15 minutes (Update Weather xx) 
- All scripts are identical except for their unique url by weather station

---

function getData() {
  SpreadsheetApp.getActiveSheet().getRange('A2').setValue('=http://mesowest.utah.edu/cgi-bin/droman/meso_table_mesowest_m.cgi?stn=TABC1&year1=2017&month1=9&day1=27&hour1=14&time=LOCAL&past=0"&GOOGLEFINANCE("GOOG","price"),"table",0)');

}

---
