
CSCE 679 — Assignment 1: HK Monthly Temperature Matrix
A D3.js interactive matrix visualization of Hong Kong's monthly temperatures over the last 10 years.

Prerequisites
A modern web browser (Chrome, Firefox, Safari, Edge)

Python 3 or Node.js (for local server)

temperature_daily.csv placed in the same folder as index.html

Running the Visualization
Both files must be served from a local HTTP server — browsers block d3.csv() when opened directly from the filesystem (file://).

Option A — Python (recommended)
bash
cd /path/to/project
python -m http.server 8080
Then open: http://localhost:8080

Option B — Node.js (npx serve)
bash
cd /path/to/project
npx serve .
Then open the URL printed in your terminal (usually http://localhost:3000).

File Structure
text
project/
├── index.html            ← visualization code (D3.js)
└── temperature_daily.csv ← HK daily temperature data
Usage
Action	Result
Click ▲ Maximum Temperature	Matrix shows monthly max temps (blue → red ramp)
Click ▼ Minimum Temperature	Matrix switches to monthly min temps (purple → yellow ramp)
Hover over any cell	Tooltip shows date, max °C, and min °C
Each cell	Contains two sparklines — green (daily max) and grey (daily min)
The color legend on the right uses a fixed numeric range shared across both modes so colors are always comparable.

CSV Format
The code auto-detects column names. It supports:

Separate columns: Year, Month, Day, Max, Min

Single date column: Date (formats YYYY-MM-DD or YYYYMMDD) + Max, Min

Column names are case-insensitive and flexible (e.g. Maximum, maximum temperature, tmax all work).