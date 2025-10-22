# SEC Share Data Viewer

A single-page web application that fetches and displays outstanding common stock share data from the U.S. Securities and Exchange Commission (SEC) EDGAR API.

This project was created to fulfill a web developer task brief. It visualizes the maximum and minimum number of outstanding shares for a given company for all fiscal years reported after 2020.

## Features

- **Live Data:** Fetches the latest available data directly from the SEC EDGAR API.
- **Dynamic Company Lookup:** Defaults to Baker Hughes (CIK: 0001701605), but can display data for any company by providing a 10-digit CIK in the URL.
- **Data Visualization:** Clearly presents the maximum and minimum share counts and their corresponding fiscal years in a clean, card-based layout.
- **Responsive Design:** The interface is fully responsive and works on devices of all sizes, from mobile phones to desktop monitors.
- **Zero Dependencies:** The entire application is contained within a single `index.html` file with no external libraries or frameworks.

## How to Use

1.  **Open the File:**
    Simply open the `index.html` file in any modern web browser.

2.  **View Data for a Different Company:**
    To view data for a different company, append a `CIK` query parameter to the URL. The CIK must be the company's 10-digit Central Index Key.

    **Example:** To view data for Apple Inc. (CIK: 0000320193), use the following URL:
    
    file:///path/to/index.html?CIK=0000320193
    

    The page will automatically fetch and display the data for the specified CIK without reloading.

## Technical Details

- **Technology Stack:** The application is built with vanilla HTML5, CSS3, and JavaScript (ES6). All code is self-contained within the `index.html` file.
- **API:** It utilizes the `companyconcept` endpoint of the SEC's EDGAR API to retrieve data for the `dei/EntityCommonStockSharesOutstanding` concept.
- **Data Processing:** Client-side JavaScript is used to:
    1.  Fetch the JSON data from the SEC.
    2.  Filter the share data to include only entries for fiscal years after 2020 from primary disclosure forms (10-K, 10-Q).
    3.  Calculate the maximum and minimum share values from the filtered dataset.
    4.  Dynamically update the DOM to display the results.

## Included Files

- `index.html`: The core web application file.
- `README.md`: This file.
- `uid.txt`: An attachment included as-is, per the project requirements.
