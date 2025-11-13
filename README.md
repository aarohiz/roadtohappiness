🌈 # Road to Happiness

Find your own happiest route — safely, beautifully, meaningfully.

🧭 ## Overview

Road to Happiness is an intelligent route recommender that personalizes navigation based on what happiness means to you.

Whether your priority is safety, scenery, vibrancy, or serenity, our system uses machine learning and open geospatial data to create routes that align with your emotional preferences — not just your destination.

Traditional maps find the shortest route.

We find the route that makes you feel happiest.

💡 ## Motivation

Walking or commuting through a city isn’t only about speed — it’s about how the journey feels.

A woman walking home at night might value well-lit, low-crime routes.

A tourist might prefer streets with murals, cafés, or landmarks.

A nature lover might want quiet roads with more trees or parks nearby.

Road to Happiness blends data science and human preference modeling to map happiness in motion.

🧠 ## Core Idea

We model each route segment as a vector of features that influence a person’s happiness, including:

| Category              | Example Features                                   | Data Sources                                                     |
| :-------------------- | :------------------------------------------------: | ---------------------------------------------------------------: |
| Safety                | Crime rate, lighting, time of day, foot traffic    | City open data (e.g., Berkeley Open Data Portal), police reports |
| Aesthetic Appeal      | Proximity to parks, public art, cafés, waterfronts | Google Places / Yelp / OSM tags                                  |
| Environmental Factors | Air quality, greenery, noise level                 | Environmental APIs                                               |
| Convenience           | Distance, slope, walkability, transit proximity    | OpenStreetMap / OSMnx                                            |

A user can specify their “happiness type” — e.g., Safe, Scenic, Social, or Peaceful — and the system uses a weighted ML model to score and rank possible routes.

⚙️ ## Methodology

1. Data Collection

Pull geospatial data from OpenStreetMap.

Overlay Berkeley’s open crime data and other context sources.

Use OSM tags (e.g., “park”, “café”, “bench”) for attractiveness scoring.

2. Feature Engineering

Normalize continuous features (e.g., crime density).

Encode categorical attributes (e.g., street type, amenity).

Combine them into a feature vector per route segment.

3. ML Modeling

Option 1: Weighted Scoring Model

Compute happiness score = Σ (feature × user-defined weight).

Option 2: Learned Model (if time permits)

Train a regression/classifier model to predict happiness ratings using user feedback or proxy labels (e.g., Yelp popularity).

4. Route Optimization

Use networkx or osmnx shortest-path algorithms.

Replace distance weights with 1 − happiness score to find the happiest route.

5. Visualization

Display the routes (safest, scenic, fastest) using Folium or Kepler.gl.

Color-code paths (green → happiest, red → least happy).

Add hoverable explanations: “Low crime, lots of cafés nearby.”

🗺️ ## Tech Stack
| Category          | Tools / Libraries                |
| :---------------- | -------------------------------: |
| Data Handling     | pandas, geopandas, numpy         |
| Mapping & Routing | osmnx, networkx, folium          |
| Machine Learning  | scikit-learn, xgboost (optional) |
| Visualization     | folium, kepler.gl, matplotlib    |
| (Optional UI)     | streamlit or notebook interface  |

🧩 ## Example Use Cases

Safe Path for Women: Recommend the lowest-crime and best-lit walking route home.

Tourist Mode: Recommend a walk that passes by murals, coffee shops, and parks.

Peaceful Path: Prioritize quiet residential streets and greenery.

Happiness Feedback: Let users rate how happy they felt on their route to improve model learning.

🧪 ## Expected Outputs

Interactive map comparing multiple routes.

Safety heatmap overlay for Berkeley.

Quantitative metrics: “Happiness score: 0.83 | Distance: 1.2 mi | ETA: 14 min.”

Visualizations and model explainability plots.

🚀 ## Future Extensions

Integrate real-time data (weather, crowd levels).

Build a feedback loop so users can “train” their happiness profile.

Deploy as a mobile web app with Streamlit or Mapbox.

Expand to multiple cities using open data portals.

❤️ ## Team Vision

We believe that technology should make people feel better, not just move faster.

By rethinking navigation through the lens of emotion and safety, Road to Happiness shows how machine learning can make the world — and each journey — a little more joyful.

📎 ## Example Output
| Route   | Distance | Happiness Score | Notes                              |
| :------ | :------: |  :------------: | ---------------------------------: |
| Route A | 1.2 mi   | 0.87            | Passes cafés and murals, low crime |
| Route B | 1.1 mi   | 0.63            | Faster but higher incident rate    |
| Route C | 1.5 mi   | 0.90            | Long but scenic through parks      |
