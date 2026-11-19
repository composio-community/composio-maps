---
name: find-places
description: Use Composio Maps to find places by description or near coordinates, look up a place's opening hours and details, get directions and travel time, or convert between addresses and coordinates.
---

## Find places and details

- The plugin loads tools on demand, so load these by their exact names when they are not already available:
  - `GOOGLE_MAPS_TEXT_SEARCH` to find places from a description. Put the place type and the city or landmark in `textQuery`, for example `"coffee shops near the Louvre in Paris"`.
  - `GOOGLE_MAPS_NEARBY_SEARCH` when the user gives coordinates: pass `latitude`, `longitude`, `radius` in meters, and `includedTypes` such as `["park"]` or `["restaurant"]`.
  - `GOOGLE_MAPS_GET_PLACE_DETAILS` with the `id` from a search result as `name`, and a `fieldMask` listing what the user asked for, such as `regularOpeningHours`, `nationalPhoneNumber`, `websiteUri` or `rating`.
- Show each place's name and address, plus rating or open status when returned. Prefer places whose `businessStatus` is operational. If a requested field is missing from the response, say so instead of guessing.

## Directions and coordinates

- For travel time or distance, call `GOOGLE_MAPS_GET_ROUTE` with `origin_address`, `destination_address`, and `travel_mode` (`DRIVE`, `WALK`, `BICYCLE` or `TRANSIT`). The response's `duration` is in seconds, such as `"3376s"`, so convert it to minutes or hours, and convert `distanceMeters` to km or miles.
- For an address's coordinates, call `GOOGLE_MAPS_GEOCODE_ADDRESS_WITH_QUERY` with the full address in `address_query`, and report the latitude, longitude and formatted address.

The plugin looks up public places and routes only. It can't track people or devices, make bookings, or read or change the user's own Google Maps lists. If access is missing, direct the user to the plugin's connection flow. If the tool reports insufficient balance, explain that the lookup could not run and stop.
