# GA-Iguana
How to extract greater than 10000 rows on Google Analytics

Simple method to extract greater than 10000 rows on Google Analytics
  - Minor "coding" skills
  - Use Google Sheets and follow simple instructions
  - Download raw data *.tsv files for all rows
  - Combine all *.tsv files into master data *.csv file using command line
  
  
Instruction (3 steps)

1. Run query to get base URLs
- 1a. Go to: https://ga-dev-tools.appspot.com/query-explorer/
  - Authorize
  - Complete "select a view" and "query parameters"
  - "Run query"

2. Update spreadsheet to one-click download n URLs
- 2a. Make a copy of this spreadsheet <a href="https://docs.google.com/spreadsheets/d/1oOBYtJIvogW8CjMcJsLjFINxa7ataJXb54qDmak7Tm0/edit#gid=449108404">this spreadsheet</a>
  - Columns
    - A: start-date 
    - B: end-date
    - C: Group (This is based off the amount of rows you want to pull. Cells can be filled in series to n groups)
    - D: Start index
    - E: Direct link to this Report (See note)
      - At bottom of page, copy "Direct link to this Report" URL and paste in E3
    - F: Populated Direct link to this Report
      - Populated Direct link to this Report
    - G: Download Results as TSV
      - At bottom of page, right click "Download Results as TSV," and click "copy link address," then paste in G3.
    - H: Populated DL URL
      - (Update the formula in H3 to match the URL pasted in G3. Note: Output is download URL with start-index updated to match D:D).
      - After updating H:H, click H3 to verify URL works (a new tab will open and start a download). When this works, open all URLs to download all files. Highlight all cells, right click, open links.
- 2b. Locate all files and put in separate folder

3. Combine all spreadsheets with terminal or command prompt (source: https://eikhart.com/blog/merge-csv-files-with-mac-os-x-terminal)
- 3a. Open terminal and locate folder. For ex:
  - cd ~/"downloads"/"new folder"
  - return
  - cat *.tsv >merged.csv
