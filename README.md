# AirportCoordinates
Simple Google AppScript that automatically looks up Airport Latitude and Longitude

# Google Sheets Airport Coordinate Lookup

This Google Apps Script automates the retrieval of latitude and longitude coordinates for airports based on their name or IATA/ICAO code (e.g., "SJC", "KLAX"). The tool integrates directly into the Google Sheets interface by adding a custom menu for a streamlined workflow.

## Prerequisites

To ensure the script functions correctly, organize your Google Sheet as follows:

| Column | Data Description |
| :--- | :--- |
| **Column A** | Airport identifiers (Name, IATA, or ICAO codes) |
| **Column B** | Target for Latitude values |
| **Column C** | Target for Longitude values |

*Note: Row 1 should be a header row; the script processes data starting from Row 2.*

## Installation

1. **Open your Google Sheet.**
2. **Access the Apps Script Editor**:
   * Navigate to **Extensions** > **Apps Script** in the top menu.
3. **Insert the Code**:
   * Delete any template code in the `Code.gs` editor window.
   * Paste the provided script into the editor window.
4. **Save the Project**:
   * Click the **Save** (disk) icon and name the project `Airport Lookup Tools`.
5. **Authorize the Script**:
   * Click the **Run** button (triangle icon).
   * When the "Authorization Required" prompt appears, click **Review Permissions**.
   * Select your Google account.
   * On the warning screen, click **Advanced** and then **Go to Airport Lookup Tools (unsafe)**.
   * Click **Allow** to grant the script access to your spreadsheet and the Google Maps Geocoding service.

## Usage

1. **Refresh the Spreadsheet**: After installation, a new menu item titled **Airport Tools** will appear in your top toolbar.
2. **Input Data**: List your airports in **Column A**.
3. **Execute**:
   * Click **Airport Tools** > **Lookup Coordinates**.
   * The script will iterate through the list and populate the corresponding coordinates in Columns B and C.

## Important Limitations

* **Daily Quotas**: Standard Google accounts are limited to 1,000 geocoding requests per day. Google Workspace accounts typically have a higher limit of 10,000.
* **Rate Limiting**: For lists exceeding 100 rows, Google may temporarily throttle requests. If the script stops prematurely, wait a moment and run it again to process the remaining rows.
* **Data Accuracy**: The script relies on the Google Maps Geocoding API. For the highest accuracy, use specific terms in Column A (e.g., "San Jose Airport" instead of just "SJC").

---
*Created for automated airport data management.*
