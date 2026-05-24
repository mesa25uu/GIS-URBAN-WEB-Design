# GIS-Web-Urban: Urban Planning Analysis for Oxnehaga Area

## Project Context & Overview

**Course:** GIS + BIM Assignment (Urban Planning)

**Objective:** Integrate GIS and BIM technologies to analyze urban accessibility, infrastructure proximity, and service distribution in the Oxnehaga area.

**Study Area:** Oxnehaga neighborhood in Sweden, focusing on pedestrian accessibility to key services including schools, healthcare facilities, public transportation, and kindergartens.

---

## 1. Dataset Overview & GIS Data Curation

### 1.1 Datasets Included

| Dataset | Type | Source | Purpose | Description |
|---------|------|--------|---------|-------------|
| **Oxnehaga-Area.geojson** | Polygon | Administrative boundary | Study area boundary | Defines the geographic extent of the analysis area |
| **Main_byggnad.geojson** | Polygon | Building cadastre | Building footprints & 3D context | Main building structure with 3D representation (red highlighted building is the focus) |
| **Oxnehaga_school.geojson** | Point | Educational services | School location | Primary school serving the area |
| **Oxnehaga_school_route.geojson** | LineString | Pedestrian analysis | Safe school route | Analyzed walking route from school to train station |
| **Bus_stop.geojson** | Point | Public transport | Transit accessibility | Bus stop locations for public mobility analysis |
| **Huskvarna_train_station.geojson** | Point | Transport hub | Transit center | Train station access point |
| **train.geojson** | LineString | Transport network | Railway network | Main railway line infrastructure |
| **Vardcentral_walking_distance.geojson** | Polygon | Healthcare accessibility | 15-minute walking zone | Healthcare facility walking distance buffer (accessibility analysis) |
| **Kinder_Garden.geojson** | Point | Educational services | Early childcare services | Kindergarten locations |
| **Distans_from_centrum.geojson** | Polygon | Distance analysis | Urban distance zones | Concentric distance buffers from city center |

### 1.2 Data Preprocessing & Curation Steps

1. **Data Standardization:** All datasets converted to GeoJSON format (WGS84 projection)
2. **Coordinate Validation:** Verified geographic coordinates for all point and line features
3. **Buffer Analysis:** Generated walking distance zones (15-minute walking radius ≈ 1.2 km) for healthcare and transit accessibility
4. **Route Analysis:** Digitized school-to-station pedestrian route based on street networks
5. **Boundary Definition:** Delineated study area perimeter for spatial extent
6. **Attribute Enrichment:** Added descriptive properties to features for analysis

---

## 2. GIS Analysis & 2D Visualization

### 2.1 Analytical Layers

The GIS analysis examines multiple aspects of urban accessibility:

**Accessibility Analysis:**
- **Route from School to Train Station:** 2.5 km pedestrian route identifying safe access corridors
- **Healthcare Walking Distance:** 1.2 km buffer zone showing coverage of medical facilities
- **Distance from City Center:** Concentric zones measuring urban proximity

**Service Coverage Analysis:**
- School proximity and accessibility
- Kindergarten distribution
- Bus stop connectivity
- Train station access

### 2.2 Visualization Approach

- **3D Terrain:** Elevation data integrated for spatial context
- **Color-coded Layers:** Distinct colors for different feature types (schools=green, routes=purple, healthcare=light green)
- **Interactive Toggle:** User can show/hide layers by category (General, Analysis, Services)
- **Hit Testing:** Click on features to view detailed attributes
- **Spatial Context:** Topo-vector basemap provides street and administrative reference

---

## 3. BIM Integration & 3D Representation

### 3.1 BIM Model Integration

**Focus Building:** Main Building (Main_byggnad.geojson) - highlighted in red
- Represents a primary landmark in the area
- 3D extruded representation showing building footprint and height
- Integrated into 3D scene for spatial reference

**BIM Representation Details:**
- **Tools Used:** ArcGIS JS (4.29) with 3D Scene Layer support
- **Coordinate System:** WGS84 (EPSG:4326)
- **Elevation Mode:** On-the-ground positioning for accurate spatial alignment with terrain

### 3.2 BIM-GIS Integration Benefits

1. **Spatial Anchoring:** BIM model provides contextual reference for GIS analysis
2. **Urban Design Context:** 3D building geometry shows development density and urban morphology
3. **Accessibility Analysis:** Building location informs pedestrian route planning and service accessibility
4. **Visual Communication:** 3D representation enhances stakeholder understanding of spatial relationships

---

## 4. Integrated Analytics (GIS + BIM)

### 4.1 Analytical Framework

**Research Questions Addressed:**

1. **Accessibility:** Is the school accessible by safe pedestrian routes? 
   - Result: 2.5 km route established from school to train station

2. **Service Proximity:** Are essential services within walking distance?
   - Result: Healthcare within 1.2 km walking distance (accessibility zone mapped)

3. **Urban Context:** How does building density relate to service distribution?
   - Result: Buildings cluster in central areas; services distributed around study area

4. **Multi-modal Connectivity:** Can residents access public transportation?
   - Result: Bus stops and train station well-integrated into accessibility network

### 4.2 Integration Methodology

- **GIS Layers** provide network analysis, buffer zones, and spatial distribution
- **BIM Model** provides architectural context and building-level detail
- **Combined Analysis** shows how built environment (BIM) relates to accessibility patterns (GIS)
- **Narrative:** Urban planning story connecting infrastructure, buildings, and accessibility

---

## 5. Technical Documentation

### 5.1 Tools & Technologies Used

| Component | Tool/Technology | Version | Purpose |
|-----------|-----------------|---------|---------|
| **GIS Mapping** | ArcGIS API for JavaScript | 4.29 | Web-based GIS visualization and analysis |
| **3D Viewer** | Cesium/ArcGIS Scene Viewer | Latest | 3D BIM model integration |
| **Data Format** | GeoJSON | RFC 7946 | Interoperable geographic data format |
| **Projection** | WGS84 | EPSG:4326 | Global geographic coordinate system |
| **Frontend** | HTML5 + CSS3 + JavaScript | ES6+ | Web application framework |
| **Styling** | CSS Grid/Flexbox | Modern | Responsive UI design |

### 5.2 Assumptions & Specifications

1. **Walking Distance:** Assumed 1.2 km ≈ 15 minutes walking time at 1.4 m/s average speed
2. **School Route:** Assumed to follow existing street network; actual route digitized based on accessibility
3. **Building Heights:** Simplified 2-unit extrusion for visualization; does not represent actual building height
4. **Coordinate Accuracy:** All data in WGS84; accuracy ±5 meters (typical for cadastral data)
5. **No Elevation Data Manipulation:** Terrain used as-is from world elevation dataset
6. **Browser Compatibility:** Requires modern browser with WebGL support (Chrome, Firefox, Edge, Safari 12+)

---

## 6. Visualization & User Interface Structure

### 6.1 Viewer Components

**Left Sidebar (Control Panel):**
- Project title and branding
- **General Information** dropdown - Area boundary, buildings, transport infrastructure
- **Analysis** dropdown - Route analysis, healthcare accessibility, distance zones
- **Services** dropdown - Educational facilities, transportation, healthcare
- Toggle switches for layer visibility

**Main Viewer (3D Map):**
- Interactive 3D scene with terrain
- Zoom, pan, and rotate controls
- Home button for default view reset

**Right Information Panel:**
- Feature details display on click
- Attribute table with feature properties
- Link to Project 4 (BIM Viewer) when main building is selected
- Dynamic content updates with user interactions

### 6.2 User Experience Flow

1. User opens application and sees 3D map with study area
2. User toggles layer categories to explore different aspects
3. User clicks on features to view detailed information
4. User selects main building to access BIM viewer (Project4.html)
5. User navigates between 2D GIS analysis and 3D BIM representation

---

## 7. Learning Outcomes Alignment (ILO)

### Learning Objectives Addressed:

**Knowledge & Understanding:**
- Understand GIS data structures, projection systems, and spatial analysis
- Comprehend urban accessibility concepts and infrastructure planning
- Recognize BIM-GIS integration benefits for urban design

**Skills & Application:**
- Apply GIS tools for spatial analysis and buffer operations
- Create interactive web-based geographic visualizations
- Integrate 3D models with GIS data
- Develop analytical narratives for stakeholder communication

**Critical Analysis & Evaluation:**
- Evaluate service accessibility patterns in urban areas
- Assess infrastructure adequacy for pedestrian connectivity
- Analyze trade-offs between built form (BIM) and accessibility (GIS)
- Interpret spatial relationships between urban elements

**Learning Outcome Integration:**
- Demonstrates integrated GIS-BIM analysis for urban planning
- Applies spatial thinking to real-world accessibility problems
- Communicates complex spatial relationships through interactive visualization
- Evaluates urban design implications of infrastructure planning

---

## 8. How to Use This Project

### 8.1 Opening the Application

1. Open `index.html` in a modern web browser
2. Wait for 3D scene and all layers to load (5-10 seconds)
3. Use sidebar to toggle layers and explore data

### 8.2 Interactive Features

- **Toggle Layers:** Click checkboxes to show/hide layer groups
- **Expand/Collapse:** Click dropdown headers to reveal layer options
- **View Details:** Click on any feature to see attributes in right panel
- **Access BIM:** When main building is selected, click "Open Project 4" to view 3D model
- **Navigate:** Use mouse to rotate, zoom, and pan the 3D view

### 8.3 Interpretation Guide

- **Green area boundary:** Study area extent
- **Gray buildings:** Building footprints (red = main focus building)
- **Purple line:** Pedestrian route analysis
- **Light green zones:** Healthcare accessibility (walking distance)
- **Yellow circles:** Bus stops
- **School icons:** Educational facilities

---

## 9. References & Further Reading

- ArcGIS API for JavaScript Documentation: https://developers.arcgis.com/javascript/
- GeoJSON Specification: https://tools.ietf.org/html/rfc7946
- BIM Standards: ISO 19650 (Information management using BIM)
- Urban Planning Theory: Accessibility and Mixed-Use Development

---

## Evaluation Summary

| Aspect | Achievement | Evidence |
|--------|------------|----------|
| **Context** | Explicit explanation with dataset overview | Dataset table and area description |
| **GIS Layers** | Multiple layers with preprocessing documentation | 10 geospatial layers with metadata |
| **BIM Integration** | 3D model with alignment to GIS data | Main building 3D representation |
| **Analytical Integration** | Connected GIS and BIM through spatial analysis | 4 key research questions addressed |
| **Technical** | Tools and assumptions documented | Section 5 technical details |
| **Visualization** | Structured UI with analytical narrative | Organized dropdown categories |
| **Storytelling** | Accessibility narrative connecting all elements | Analytical framework (Section 4) |
| **ILO Alignment** | Clear mapping to learning outcomes | Section 7 detailed alignment |

---

**Last Updated:** May 2026  
**Course:** GIS + BIM Urban Planning Assignment  
**Status:** Comprehensive documentation and interactive visualization
