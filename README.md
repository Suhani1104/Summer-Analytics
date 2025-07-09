# Summer-Analytics
### Overview:
This project implements a real-time, data-driven dynamic pricing engine for urban parking lots. The system ingests live data streams from city parking spaces and applies economic and data science principles to dynamically update parking prices. The primary objectives are to optimize utilization, reduce congestion, and maximize revenue by adjusting prices based on demand, environmental factors, and competition.

### Tech Stack
Python 3
Pandas: Data manipulation and analysis
NumPy: Numerical computations
Bokeh: Interactive data visualization
Panel: Dashboard and web app integration
Google Colab: Development and execution environment

### Architecture Diagram
flowchart TD
    A[Data Source: Parking Lot Sensors<br/>(CSV Stream)] --> B[Data Ingestion]
    B --> C[Feature Engineering<br/>(Pandas/Numpy)]
    C --> D[Dynamic Pricing Models]
    D --> E[Real-Time Price Output]
    E --> F[Bokeh Visualization]
    F --> G[Panel Dashboard]


### Project Architecture & Workflow
1. Data Ingestion
Source: Simulated real-time data from parking lots, including occupancy, capacity, queue length, vehicle type, traffic, and special event indicators.
Method: The dataset is loaded into a DataFrame from a local upload or a Google Drive link.

2. Feature Engineering
Datetime Construction: Combines LastUpdatedDate and LastUpdatedTime into a single LastUpdatedDateTime column for accurate time series analysis.
Derived Features:
Occupancy Rate: Calculated as Occupancy / Capacity.
Traffic Condition Numeric: Encoded as 1 (low), 2 (medium), 3 (high).
Vehicle Type Numeric: Encoded as 1 (car), 0.5 (bike), 1.5 (truck).

3. Dynamic Pricing Model
Pricing Formula:
The price is calculated as a weighted sum of:
Occupancy rate
Queue length
Traffic condition
Special day indicator
Vehicle type
Constraints:
Prices are clamped between $5 and $25 to ensure stability and fairness.

4. Real-Time Processing
All transformations and price computations occur as new data is ingested, enabling real-time updates and analytics.

5. Visualization & Output
Bokeh: Interactive plots display price trends for each lot.
Panel: Serves the dashboard as a web app for monitoring and analysis
