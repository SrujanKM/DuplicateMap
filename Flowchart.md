START
  |
  v
User uploads land map PDF
  |
  v
Generate Unique ID for uploaded PDF
  |
  v
Identify Village Name
  |
  v
Store PDF in Village-specific folder
  |
  v
Check number of PDFs in that Village folder
  |
  v
IF only 1 PDF present
  |
  └──> Mark as "No comparison needed"to 
        |
        v
       END
  |
  v
IF more than 1 PDF present
  |
  v
Select FIRST PDF as Reference Map
  |
  v
FOR each remaining PDF in the folder
  |
  v
Convert both PDFs to high-resolution images
  |
  v
Preprocess images
(Remove noise, improve clarity, deskew)
  |
  v
Compare Overall Map Structure
(Shape & layout similarity)
  |
  v
Extract Polygons from both maps
  |
  v
Compare Polygon Shapes
(Area overlap & boundary similarity)
  |
  v
Extract Polygon Numbers using OCR (Marathi)
  |
  v
Compare Extracted Text
(Handles minor OCR errors)
  |
  v
Calculate Final Similarity Score
  |
  v
Final Score =
  (40% Structure Match) +
  (40% Polygon Match) +
  (20% Text Match)
  |
  v
IF Final Score ≥ 95%
  |
  ├──> Mark PDFs as DUPLICATES
  |     |
  |     v
  |   Store result in Log File
  |
  v
ELSE
  |
  └──> Mark PDFs as UNIQUE
        |
        v
       Continue comparison
  |
  v
END FOR
  |
  v
END
