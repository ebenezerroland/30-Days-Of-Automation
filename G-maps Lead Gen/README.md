Google Maps to Google Sheets Workflow (n8n)

This workflow leverages n8n to automate Google Maps API queries and log structured location data into Google Sheets, based on a list of ZIP codes and categories.



Features
- Queries Google Maps API using ZIP codes + subcategories  
- Writes results to Google Sheets, cleans duplicates  
- Handles API rate limits with exponential backoff  
- Logs statuses directly in the sheet for tracking



Requirements
- Google OAuth credentials** (Maps + Sheets API access)
- Google Sheet with:
  - ZIP codes (e.g., in a sheet named `AZ Zips`)
  - Subcategories (e.g., in `Google Maps Categories`)
- A configured **n8n instance**



Setup Steps
1. Prepare Sheets
   Add ZIPs and subcategories to your Google Sheet. Paste the URL in the `Settings` node.

2. API Setup
   Connect Google OAuth in n8n. Ensure access to `places.searchText` endpoint.

3. Customize
   Edit the `textQuery` fields in the API node to your needs. Set manual/scheduled runs.

4. Run the Workflow  
   Manual or recurring — your choice.


Notes
- Uses retries with exponential backoff to reduce API errors.
- All output is neatly logged in Google Sheets.
- Reach out for help or improvements.
