# Zurich Microclimate Explorer

**Advanced GIS – Assignment 3 | ETH Zürich, FS26**

An interactive web map visualizing SenseBox environmental sensor data collected across two walking routes in Zurich (May 12–13, 2026), compared against historical citizen-science measurements from the OpenSenseMap network.

🔗 **Live app:** https://linm5.github.io/zurich-microclimate

---

## Theme

Microclimate validation across Zurich — comparing personal SenseBox readings collected near the official Flüntern weather station against fixed citizen-science reference stations, revealing microclimatic differences between Zollikon and the urban centre.

---

## Data

### SenseBox Data (Primary)
- Collected with a SenseBox MCU on two walking routes
- **Route 1:** Zollikon → ETH Hönggerberg → Cafe Europa (May 12, 17:15–18:20)
- **Route 2:** Zollikon → Tiefenbrunnen → Zurich HB → Zoo → Flüntern (May 13, 09:45–10:37)
- **Sensors:** Temperature (HDC1080 & BMP280), Humidity, Pressure, Light (TSL45315), UV (VEML6070)
- **Total readings:** 4,571 GPS-tagged measurements
- Published as a hosted feature layer on ArcGIS Online

### External Data (OpenSenseMap API)
- Historical measurements from nearby citizen-science senseBox stations
- Queried via the OpenSenseMap REST API for the collection period (May 12–13, 2026)
- Endpoint: `https://api.opensensemap.org/boxes?near=8.548,47.370&maxDistance=8000`

---

## Features

- 🗺 Satellite basemap centered on Zurich
- 🟠 SenseBox route points coloured by temperature (cold → hot gradient)
- 🟦 OpenSenseMap reference stations with historical average temperatures
- 🎚 Temperature filter slider to isolate specific temperature ranges
- 🔁 Layer visibility toggles for each data layer
- 💬 Popups on every point showing full sensor readings
- 🔍 Search, Home, ScaleBar widgets
- 📋 About, Legal Notice, and Privacy sections

---

## Structure

```
index.html        — Single-file web application (HTML + CSS + JS)
README.md         — This file
```

The app is built with:
- **ArcGIS Maps SDK for JavaScript** (v4.29) — map, widgets, graphics
- **OpenSenseMap REST API** — external sensor data
- **Embedded JSON dataset** — SenseBox readings (sampled every 3rd point)

---

## License

SenseBox data collected by the author is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
OpenSenseMap data is published under CC BY 4.0 by respective station owners.
Basemap imagery provided by Esri under the Esri Master Agreement.
