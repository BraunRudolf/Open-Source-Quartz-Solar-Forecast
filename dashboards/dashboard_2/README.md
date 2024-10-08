# Streamlit Dashboard for Open Source Quartz Solar Forecast

This Streamlit Dashboard provides an interactive interface for running and visualizing solar forecasts using the [Open Source Quartz Solar Forecast](https://github.com/openclimatefix/Open-Source-Quartz-Solar-Forecast) model developed by [Open Climate Fix](https://openclimatefix.org/).


https://github.com/user-attachments/assets/a7b1d3ac-b2c0-4c0d-bf23-45ebbbda9b88


## Features

- Configure PV site parameters (latitude, longitude, capacity)
- Select inverter type (No Inverter, Enphase, Solis, GivEnergy, or Solarman)
- Enphase API authentication flow (if applicable)
- Run solar forecast
- Visualize forecast results with interactive charts
- Compare forecasts with and without recent PV data (if applicable)
- Display raw forecast data and provide an option to download it as CSV

## Development Environment Setup

1. Clone the repository and install all the dependencies in a virtual environment on a Linux System(or WSL):
   `pip install -e .` and `pip install -r requirements.txt`

2. Set up environment variables for your inverter (if applicable):

- Create a `.env` file in your root directory
- Check out `.env.example` file and copy paste the contents of the file in the `.env` file that you just created
- Replace the placeholder for all the variables that are relevant to your inverter

## How to Run the Backend

1. Navigate to the `api` directory

2. Run the API: `python main.py`

3. Ensure that this API is running before you use the frontend

## How to Run the Frontend

1. Navigate to the `dashboards/dashboard_2` directory.

2. Run the Streamlit app: `streamlit run app.py`

3. Open your web browser and go to the URL provided by Streamlit (usually `http://localhost:8501`).

## Using the App

1. **Configure PV Site:**

- Use the sidebar to input latitude, longitude, and capacity of the PV site.
- Alternatively, check "Use Default Values" to use pre-set values.

2. **Select Inverter Type:**

- Choose between "No Inverter", "Enphase", "Solis", "GivEnergy", and "Solarman" from the dropdown menu.

3. **Enphase Authorization (if applicable):**

- If you select Enphase, follow the authorization process:
  - Click the provided authorization URL
  - Grant permissions on the Enphase website
  - Copy the redirect URL and paste it back into the app

4. **Run Forecast:**

- Click the "Run Forecast" button to generate predictions.

5. **View Results:**

- See current power, total forecasted energy, and peak forecasted power.
- Examine the interactive line chart comparing forecasts with and without recent PV data.
- Review the raw forecast data table and optionally download it as CSV for further processing.

## Additional Information

- Forecasts are generated for the next 48 hours in 15-minute intervals.
- The app demonstrates the impact of using recent PV data (from Enphase) on forecast accuracy.
