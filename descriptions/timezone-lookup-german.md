**Title:** Resolve timezone from German-language birthplace input

---

Sub-workflow that takes birthplace city/country fields (including German labels) and returns the matching timezone via GeoNames.

## How it works

1. Triggered via **Execute Workflow Trigger** with input like:
   - `Geburtsort` (city)
   - `Geburtsland` (country)
2. Maps country names (German/English variants) to ISO country codes
3. Searches city coordinates through GeoNames `searchJSON`
4. Looks up timezone with GeoNames `timezoneJSON`

## Setup

1. Replace `YOUR_GEONAMES_USERNAME` in both GeoNames URLs with your GeoNames username
2. Call this as a sub-workflow and pass city/country fields

## Customization

- **Country mapping:** extend `countryMap` in **Map Country Code**
- **Input keys:** support additional aliases beyond `Geburtsort` / `Geburtsland`
- **Search behavior:** increase `maxRows` or add fallback matching logic for ambiguous city names
