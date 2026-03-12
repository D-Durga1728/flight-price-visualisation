# Price Evolution Analytics Flight Data Visualisation Analysis.  

FlightPrice_Evolution is a data visualisation project that investigates the change in price of airline tickets with a closer departure date. We scraped a huge data set at Expedia, performed some data wrangling, and crammed it into a series of interactive plots in order to identify pricing patterns. I covered this as my CSC1143 Data Visualisation course project.  

---
## Run the Project in Google Colab

This project is designed to run in Google Colab because the dataset processing requires more memory than typical local environments.

---

# Project Overview  

The airline ticket prices fluctuate and wildly due to the boom in demand, the strategies of airlines and the time before you fly runs out. The awareness of these swings can assist the travellers to determine the day that suits them most to purchase a ticket.  

The primary objective of this project is to determine the behaviour of prices within the 30 days to flight with the help of a bulky flight data.  

The data sources are Expedia flights between 16 large airports in the US in April through October 2022.  

We were preoccupied with the identification of trends because the departure date is on the verge.  

---

# Dataset  

Source: Kaggle Flight Prices Dataset.  

Dataset characteristics:  
- Original size: 31 GB  
- Total rows: 82 million+  
- Columns: 27 variables  
- Airports: 16 US hubs  
- Data period: April‑October 2022  

It is enormous hence we cut it into bits to ensure that memory is not an issue.  

Filtered dataset characteristics:  
- Rows: 3,569,724  
- Size: ~138 MB  
- Type of ticket: Basic Economy only.  
- Flights: Non‑stop only  

Selected variables:  

- searchDate  
- flightDate  
- totalFare  
- startingAirport  
- destinationAirport  
- isBasicEconomy  
- isNonStop  

A brand‑new feature we made:  

- days beforeFlight = flightDate - searchDate  

---

## Running the Notebook

To run the project:

1. Click the **Open in Colab** button above.
2. Mount your Google Drive in Colab:

Run the following code cell to access your dataset stored in Google Drive:

from google.colab import drive
 drive.mount('/content/drive') 

3. Ensure the dataset path matches the location in your Google Drive.
4. Run the notebook cells sequentially.

The notebook performs data processing, feature creation, and visualization of flight price evolution.

---

# Data Preprocessing  

The prep step had a few moves:  

1. To ensure that the RAM did not run out, we loaded the huge data in blocks using Pandas.  
2. Filtered to keep only:  
   - Basic economy tickets  
   - Non‑stop flights  
3. Selected a sub-set of columns, which are important in analysis.  
4. Added the new daysBeforeFlight column to count the number of days between search and departure.  
5. In order to make the visual simple we have considered the five most frequent routes in the data only.  

---
# Routes Analysed  

These five are brought nearer in the last plot:  

- SFO -LAX (San Francisco Los Angeles)  
- LAX -SFO (Los Angeles -San Francisco)  
- ORD – LGA (Chicago – New York)  
- LGA – ORD (New York – Chicago)  
- EWR – BOS (Newark – Boston)  

These are the most common trips that most individuals visit and thus they are fairly representative.  

---
# Exploratory Data Analysis  

I plunged into the prices bouncing across the months before I struck the last plot. I threw together a boxplot to eyeballs month-by-month spread.  

Important lesson learned: the price ranges appear funkily similar every month, and this fact led to the conclusion that it was reasonable to have one average ticket price across the entire data set at the final visual.  

---
# Visualization  

The primary feature is an animated horizontal bar chart that was created using Plotly.  

What it shows:  

- The number of days of flight reflects on each frame.  
- Time window: 30 days before takeoff 1 day before takeoff.  
- Bars = various paths of flights.  
- Value displayed: average fare in that route.  
- Play/pause controls Interactive slider allows you to march the timeline.  

Through the animation, the user can see the increase in price an hour before the departure.  

---
# Insights  

A few things stuck out:  

- The bigger the distance between the flight date and the present, the higher the price becomes.  
- The approximate positions of the wave-shaped bumps are:  
  - 20 days out  
  - 13 days out  
  - 5 days out  
  - 1 day out  

These spikes are repeated in several routes, which points to an overlapping pricing pn.  

Overall, purchase of tickets immediately before the flight is normally associated with a premium price.  

---
# Technologies Used  

- Python - data analysis and work.  
- Pandas – data wrangling.  
- Plotly - interactive drawing/animation.  
- Jupyter Notebook do the analysis.  
- Google Colab - processing the large data.


---
# Limitations

To a great extent this visualisation is based on animation. When you consider one still image, much of the insight is lost due to the fact that the principal thing is the change with time.

The other drawback is that we are using the airport codes and that may not be readily recognisable to all.

---
# Ethical and Legal Factors.

No personal identifiers were present in our data set; it is merely a flight itinerary information.

- This is an academic analysis project.
- The actual value application would have to take into account:
  - Data privacy regulations
  - Proper utilisation of pricing information.
  - Openness in the findings of the analysis.

---

## Note

Due to the large dataset size, the project is intended to run in Google Colab rather than a local environment.
