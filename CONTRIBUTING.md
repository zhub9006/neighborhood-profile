# Contributing to Neighborhood Profiles

Thank you for your interest in contributing! This repository aims to collect open-source neighborhood profile data from OpenStreetMap.

## How to Add a New Neighborhood

1. Fork this repository
2. Create a new branch for your neighborhood data
3. Add your data file in the `data/` directory following the JSON schema
4. Include a README section for your neighborhood
5. Submit a Pull Request with details about your data sources

## Data Format

Neighborhood data should include:
- Location coordinates and address
- Walkability scores (from OSM-based analysis)
- Amenities within a defined radius (default 1km)
- Data collection metadata (source, date, method)

## Data Sources

All data should be sourced from OpenStreetMap (ODbL 1.0) or other open data sources.

## Guidelines

- Verify data freshness (OSM data changes over time)
- Include distance measurements for all amenities
- Use standardized categories (groceries, cafes, transit, etc.)

## PR for Nob Hill Data

This branch contains the initial contribution for Nob Hill / Northwest District neighborhood profile data.