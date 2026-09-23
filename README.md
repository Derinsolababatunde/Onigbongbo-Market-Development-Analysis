# Onigbongbo-Market-Development-Analysis
Spatial Questions to Market Data
# Onigbongbo LCDA Market and Development Analysis

## Project Overview
This project investigates the relationship between land market dynamics and physical development in Onigbongbo LCDA, Lagos State, Nigeria. **Sprint 2** focuses on extracting current market price signals using AI-assisted Google searches.

## Study Area
**Location:** Onigbongbo LCDA, Ikeja LGA, Lagos State, Nigeria

**Five Wards (Towns):**
1. Opebi
2. Oregun
3. GRA (Ikeja GRA)
4. Wasimi
5. Onigbongbo

## Sprint 2: Spatial Questions to Market Data

### Workflow
This notebook performs an **AI-assisted market analysis** workflow:

1. **Input:** Upload GeoJSON file from Sprint 1 containing the five towns
2. **Extract:** Automatically identify town names from GeoJSON properties
3. **Search:** Use SerpApi to query Google for current land prices in each town
4. **Parse:** Extract market price signals from AI Overview responses
5. **Aggregate:** Build structured market dataset (CSV + JSON)
6. **Export:** Download market_dataset.csv for further analysis

### Research Question
**What does the current land market look like in Onigbongbo?**
- Use available market information to derive indicative current market price ranges
- Leverage AI-assisted Google searches to capture real-time market signals

### Technology Stack
- **Google Colab** - Notebook environment
- **SerpApi** - AI-powered Google search integration
- **Python** - Data processing and extraction
  - `pandas` - Data manipulation
  - `json` - Market data serialization
- **QGIS** - Sprint 1: spatial boundary analysis

### Outputs

**market_dataset.csv**
- Structure: One row per town/search query
- Columns: town, query, price_signal, price_range_low, price_range_high, search_text, references
- Contains current market pricing information for each of the five wards

**market_dataset.json**
- Machine-readable version of market_dataset.csv
- Maintains references and detailed search results

**ai_overview_raw.json**
- Raw AI Overview responses from SerpApi
- Includes search queries, extracted text, and reference links for validation

## How to Use This Notebook

### Prerequisites
1. Download your **Onigbongbo_5Wards.geojson** from Sprint 1 (QGIS export)
2. Create a [SerpApi account](https://serpapi.com/) and get your API key
3. Open this notebook in Google Colab

### Steps
1. **Install packages** - Run cell 0
2. **Configure SerpApi key** - Paste your API key (cell 1)
3. **Upload GeoJSON** - Upload your five-town GeoJSON file (cell 2)
4. **Extract towns** - Notebook automatically reads town names (cell 3)
5. **Search for prices** - Notebook runs searches for each town (cell 4-6)
6. **Inspect results** - Review market signals in cells 7-8
7. **Export datasets** - Download CSV, JSON, and raw API responses (cell 9)

### Key Findings
[Add your specific market findings here after running the notebook]

## Dataset Structure

### market_dataset.csv columns:
- `town` - Ward/town name
- `query` - Search query used (e.g., "Land price Opebi Lagos Nigeria")
- `price_signal` - Extracted price indication from search
- `price_range_low` - Low end of price range (NGN)
- `price_range_high` - High end of price range (NGN)
- `search_text` - Full AI Overview text response
- `references` - Source links and citations

## Important Notes

### Data Privacy
- **Keep your SerpApi key private** - Never commit this notebook or your key to public GitHub
- Use Colab Secrets or prompt input for API key (not hard-coded)

### Limitations
- AI Overview responses vary based on Google's current search index
- Market prices are estimates from web sources (not official valuations)
- Search results reflect online market signals, not comprehensive property records
- Temporal snapshot: reflects market data at time of search

### Next Steps (Sprint 3)
- Correlate market prices with satellite-based development metrics
- Compare market signals with observed physical changes (2019-2024)
- Validate findings against official Lagos State land records

## Files in This Repository
