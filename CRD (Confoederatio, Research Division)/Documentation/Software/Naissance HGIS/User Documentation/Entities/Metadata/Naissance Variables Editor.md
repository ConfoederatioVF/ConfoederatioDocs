> [!WARNING]
> Documentation of this nature on Confoederatio Docs are user-facing only. Technical documentation should be assigned their own subdomain in the future.

The **Variables Editor** in [[Naissance HGIS]] determines when variables are mutated to a specific keyframe. This relies on a spreadsheet editor in which the `A` Column is always reserved for a date string, and the rest of the row for any potential variable names that they may contain.

Variables in the keyframe display should update instantly and be reflective of changes in the editor.
## Special Columns/Rows:

`A Column`: YYYY.MM.DD.HH.MM. (i.e. `-3000.11.20.15.03`). 
- May contain leading zeroes. Negative numbers represent BC, Positive numbers represent AD. If populated at that row, the rest of the row will be treated as values that should be pushed to the [[History]] of the corresponding entity.
`1 Row`: string
- If the A column is populated, then the first row of each spreadsheet will become the CSV-style header from which variable names are drawn.