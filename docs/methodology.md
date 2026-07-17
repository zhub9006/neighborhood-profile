# Walkability Scoring Methodology

## Overview

This document describes the methodology used to calculate neighborhood walkability and amenity scores for each profiled location. All data is sourced from OpenStreetMap (ODbL 1.0) and analyzed using OSRM routing and OSM-based spatial queries.

## Scoring Categories

Each neighborhood is evaluated across the following categories, each receiving a score from 0 to 10:

| Category | Description |
|----------|-------------|
| **Walk Score** | Overall walkability based on pedestrian access to daily errands |
| **Transit Score** | Quality and proximity of public transportation options |
| **Bike Score** | Bicycle infrastructure and nearby bike amenities |
| **Groceries** | Access to grocery stores and markets |
| **Restaurants** | Density and diversity of dining options |
| **Healthcare** | Proximity to medical facilities and pharmacies |
| **Education** | Availability of schools and educational institutions |
| **Parks** | Access to green spaces, playgrounds, and recreation areas |
| **Sports/Fitness** | Availability of gyms, sports facilities, and recreation centers |
| **Shopping** | Proximity to retail shops and services |
| **Services** | Access to banks, post offices, and other essential services |
| **Entertainment** | Availability of cultural venues, cinemas, and theaters |

## Scoring Method

1. **Data Collection**: Amenities are identified within a 1km radius of the target coordinates using OpenStreetMap queries filtered by category (amenity, shop, leisure, tourism, food).

2. **Distance Calculation**: OSRM routing is used to compute walking distances rather than straight-line (Euclidean) distances, providing more accurate real-world accessibility estimates.

3. **Score Assignment**: Each category is scored based on:
   - **Count**: Number of amenities within the radius
   - **Proximity**: Average and nearest distances to amenities
   - **Diversity**: Variety of subtypes (e.g., cuisines for restaurants, types for shops)
   - **Quality**: Whether amenities include key features (e.g., outdoor seating, wheelchair access)

4. **Normalization**: Raw counts and distances are normalized against known benchmarks to produce a 0–10 score:
   - Restaurants: Density benchmarks for urban vs. suburban
   - Grocery: Store count per km threshold
   - Healthcare: Nearest-facility distance priority
   - Transit: Stop count + average walk time to nearest stop

## Data Sources

- **Primary**: OpenStreetMap (Data © OpenStreetMap contributors, ODbL 1.0)
- **Routing**: OSRM (Open Source Routing Machine)
- **Analysis Radius**: 1000 meters (1km)

## OSM Attribution

All OpenStreetMap data is licensed under the Open Database License (ODbL) 1.0.

> Data © OpenStreetMap contributors, ODbL 1.0

## How to Contribute Methodology Updates

1. Verify any new scoring thresholds against current OSM data
2. Open an issue to discuss methodology changes
3. Submit a Pull Request with your proposed scoring updates

## Last Updated

2026-07-15
