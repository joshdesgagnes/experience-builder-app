# experience-builder-app

The main folder in the master branch stores my original Experience Builder Developer Edition App with the two custom widgets.

The my-updates branch is used to store all updated version. Currently storing v2 as the most recent.

gh-pages branch is used to host the most recent version of the app on my github page.

---
## About the App

The **Incident Reporting App** empowers communities and organizations to crowdsource public incidents directly onto a shared web map. Designed with ease-of-use and flexibility in mind, this app is ideal for:

- Neighborhood watch groups
- Municipal incident reporting
- Event coordination
- Disaster relief coordination
- Urban planning and public feedback

The application is built using **ArcGIS Experience Builder Developer Edition**, allowing for full control over layout, interactivity, and integration with ArcGIS web maps and feature services.

---
```markdown
# Experience Builder - Incident Reporting App

This ArcGIS Experience Builder app allows users to **report**, **view**, and **search** public incidents on an interactive map. Built using custom widgets, the application integrates seamlessly with ArcGIS Online's feature layers to enable real-time community-driven geographic incident tracking.

## Custom Widgets

### 1. `map-view`
A rich map-centric widget that enables users to:
- Visualize incident reports on a web map.
- Submit new incidents with form inputs and location picking.
- Attach an image to the report.
- Auto-locate the user's position with animated ripples.
- Search and filter existing reports.
- Drag and reposition the incident search panel for improved UX.

#### Features
- **User Location Detection** with animated feedback.
- **Form-based Incident Submission** with validation.
- **Image Attachment** support for uploaded files.
- **Search & Filter** functionality for past reports.
- **Zoom to Selected Incidents**.
- **Real-time Sync** with ArcGIS Feature Layers.
- **Draggable Dropdown Search** UI component.

### 2. `vgi-feed`
A lightweight, list-based widget for:
- Displaying a **live feed** of recent incident reports.
- Filtering results by **keywords**.
- Viewing essential metadata for each report.

#### Features
- Pulls incident data from the same feature layer as the map-view widget.
- Clean UX design optimized for rapid scanning and filtering.
- Keyword-based **client-side filtering**.

## Installation

1. Clone this repository or install your widgets into your existing Experience Builder environment:
   
   git clone https://github.com/your-org/incident-reporting-exb.git
   cd incident-reporting-exb

2. Copy the `map-view` and `vgi-feed` widgets into your Experience Builder `client/your-extensions/widgets` directory.

3. Run the Experience Builder development server:

   npm start

4. Add the custom widgets into your app via the Experience Builder editor.
```
---
## Configuration

### `map-view` Widget
- Set the **web map data source**.
- Ensure the feature layer URL is correct and supports `addFeatures` and `addAttachment`.

### `vgi-feed` Widget
- No additional setup required beyond layer URL.
- Customize styles via `vgi-feed-styles.css`.

## Feature Layer

Ensure the following feature service is accessible and editable:
```
https://services1.arcgis.com/KsnB2VOAvO5LjdB4/arcgis/rest/services/Incident_Reporting_Layer/FeatureServer/0
```

The layer should include the following fields:
- `Title` (Text)
- `Description` (Text)
- `Category` (Text)
- `DateAndTime` (Date)
- Optional: Attachments enabled

## Future Improvements
- User authentication for report submissions
- Display images in incident feed and provide interactivity between incident feed items and the map.
- Cleaner, customized popups.
- Better mobile UI and functionality

---
## References

- [ArcGIS Experience Builder Developer Guide](https://developers.arcgis.com/experience-builder/)
- [ArcGIS Experience Builder Resources (Esri)](https://www.esri.com/en-us/arcgis/products/arcgis-experience-builder/resources)
- [Experience Builder Dev Edition - ECCE Blog (Jan 2024)](https://ecce.esri.ca/blog/2024/01/02/experience-builder-dev-edition/)
- [ArcGIS Experience Builder SDK Resources (GitHub)](https://github.com/Esri/arcgis-experience-builder-sdk-resources)
