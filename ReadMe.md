
CSCE 679 — Assignment 1: HK Monthly Temperature Matrix
A D3.js interactive matrix visualization of Hong Kong's monthly maximum and minimum temperatures over the last 10 years.

📋 Prerequisites
A modern web browser (Chrome, Firefox, Safari, or Edge)

Python 3 or Node.js installed (to run a local HTTP server)

temperature_daily.csv placed in the same folder as index.html

🗂 File Structure
text
project/
├── index.html              # D3.js visualization
├── temperature_daily.csv   # HK daily temperature data
└── README.md
🚀 Running the Visualization
⚠️ The page must be served via a local HTTP server. Browsers block d3.csv() when files are opened directly from the filesystem (file://).

Option A — Python (recommended)
bash
cd /path/to/project
python -m http.server 8080
Then open http://localhost:8080 in your browser.

Option B — Node.js
bash
cd /path/to/project
npx serve .
Then open the URL shown in your terminal (usually http://localhost:3000).

🖱 How to Use
Action	Result
Click ▲ Maximum Temperature	Colors cells by monthly max temp (blue → red ramp)
Click ▼ Minimum Temperature	Colors cells by monthly min temp (purple → yellow ramp)
Hover over any cell	Tooltip shows Date: YYYY-MM, max °C, and min °C
Sparklines inside each cell	Green line = daily max · Grey line = daily min
The color legend on the right uses a fixed numeric range shared across both modes so temperatures remain directly comparable when toggling.

📄 CSV Format
The code auto-detects column names and supports the following layouts:

Layout A — Separate date columns:

text
Year, Month, Day, Max, Min
2015, 1, 1, 18.2, 10.5
Layout B — Single date string:

text
Date, Max, Min
2015-01-01, 18.2, 10.5
Column names are case-insensitive. Variants like Maximum, tmax, and maximum temperature are all recognized automatically.

🛠 Built With
D3.js v7 — data-driven visualization

Vanilla HTML/CSS/JavaScript — no build tools required