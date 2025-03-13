### Efficient Prompt for Converting Baseball Prospect Rankings into CSV Format

**Task Description:**
Convert a baseball prospect ranking article (typically from PDFs or web articles) into a structured CSV file.

**CSV Columns Required:**
- **First Name**
- **Last Name**
- **Position**
- **Team Abbreviation** (using abbreviations from an existing MLB teams CSV)
- **Rank**

**Process to Follow:**

1. **Extract Text Clearly:**
   - Use robust PDF extraction tools such as `pdfplumber` for PDFs or suitable text-scraping methods for web articles.

2. **Identify Clear Patterns:**
   - Rankings usually follow formats such as:
     ```
     Rank
     First Last
     Position
     TEAM NAME
     ```
   - Confirm this structure explicitly by reviewing an extracted text snippet.

3. **Use Regex for Accuracy:**
   - Employ a clear regex pattern that explicitly captures:
     - Numeric Rank
     - Full Name
     - Position
     - Full Team Name
   
   **Example regex:**
   ```regex
   \n(\d{1,3})\n([A-Za-z'\-\. ]+)\n([A-Z/]+)\n([A-Z\s]+)\n
   ```

4. **Split Names and Map Teams:**
   - Split full names explicitly into First and Last Names.
   - Map full team names to their abbreviations using a reliable MLB teams CSV file.

5. **Data Validation:**
   - Display samples of extracted data at each step to ensure accuracy.

6. **Final CSV Creation:**
   - Ensure correct ordering of CSV columns:
     ```
     First Name, Last Name, Position, Team Abbreviation, Rank
     ```

**Handling Issues:**
- If the PDF extraction method initially fails, try an alternative method (`pdfplumber` or OCR if necessary).
- Clearly verify patterns with larger snippets of extracted text if initial regex extraction fails.

This structured approach ensures rapid, accurate data extraction, minimizing rework and errors in future similar tasks.
