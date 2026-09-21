# Integrated Pothole Detection and Maintenance System

A unified operational dashboard and incident management console for monitoring, analyzing, and resolving road hazard reports in real time.

## Overview

The Integrated Pothole Detection and Maintenance System provides municipal authorities and field teams with real-time geospatial intelligence on road conditions. It aggregates citizen and sensor reports, identifies critical hazard clusters, and streamlines resolution tracking through an interactive map interface.

## Key Features

- **Interactive Geospatial Visualization**: Switch between density heatmaps for corridor-level pattern analysis and interactive scatter plots for individual cluster inspection.
- **Incident Clustering & Severity Triage**: Automatically groups proximate reports and assigns severity tiers (Low, Medium, High) based on report frequency and density.
- **Role-Based Access Control**:
  - **Standard Users**: View road safety density, browse active hazard zones, and inspect regional clusters.
  - **Administrators**: Access raw pothole records, filter by status or duplicate flags, export data to CSV, and mark clusters as resolved directly from the map surface.
- **Resolution Tracking & Audit Log**: Records maintenance actions with timestamps, technician details, and resolved pothole counts.
- **Real-Time Data Sync**: Backed by Firebase Realtime Database for live incident ingestion and persistence.
- **Adaptive UI**: Custom light and dark themes with dedicated workspace panels and session persistence.

## Tech Stack

- **Application Framework**: [Streamlit](https://streamlit.io/)
- **Geospatial & Mapping**: [PyDeck](https://deckgl.readthedocs.io/) (Deck.gl)
- **Data Manipulation**: [Pandas](https://pandas.pydata.org/)
- **Backend & Database**: Firebase Realtime Database via `firebase-admin`

## Getting Started

### Prerequisites

- Python 3.10+
- A Firebase project with Realtime Database enabled

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/goliar123/mini_project.git
   cd mini_project
   ```

2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install required packages:
   ```bash
   pip install -r frontend/requirements.txt
   ```

### Configuration

Set up your Firebase credentials and operational settings:

1. Copy the example configuration file:
   ```bash
   cp .streamlit/secrets.toml.example .streamlit/secrets.toml
   ```

2. Populate `.streamlit/secrets.toml` with your Firebase database URL, admin credentials, and service account key.

### Running the Application

Launch the Streamlit app:

```bash
streamlit run frontend/main.py
```

The application will open in your browser at `http://localhost:8501`.

## Project Structure

```
├── frontend/
│   ├── app/
│   │   ├── auth/          # Authentication, sessions, and user storage
│   │   ├── data/          # Firebase client and database references
│   │   ├── services/      # Clustering, coordinate normalization, and location
│   │   └── ui/            # Layout components, map views, and custom CSS
│   ├── tests/             # Unit and session test cases
│   ├── main.py            # Application entrypoint
│   └── requirements.txt   # Python dependencies
├── .streamlit/            # Streamlit secrets and configuration
└── README.md
```

## License

This project is licensed under the MIT License.
