## Convert PDF to CSV

## Task

* Convert the attached baseball prospect ranking article into a CSV file with the following specifications

## CSV Columns
- `First Name`  
- `Last Name`  
- `Position`  
- `Team Abbreviation` (use abbreviations from provided MLB teams CSV)  
- `Rank`

##  Matching Instructions
- Map the full team names from the article exactly to the provided MLB teams abbreviations from the attached CSV file (`mlb_teams.csv`).  
- Allow minor variations in player name formats (e.g., middle initials, suffixes).

##  Data Extraction Guidelines
- Clearly extract text from PDFs or web articles using robust text extraction methods.  
- If data is from a PDF, use `pdfplumber` for best accuracy.
- Identify and confirm the specific ranking entry format, typically structured as:
  ```
  Rank
  Player Name
  Position
  Full Team Name
  ```

## CSV Output
- Verify extracted data with sample outputs to confirm accuracy before saving.  
- Provide the final CSV file clearly structured and sorted by `Rank`.