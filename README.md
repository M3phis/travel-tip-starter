# TravelTip

#### A map-based location management web app that allows users to add, update, remove, and search locations. Locations are rendered with distance information, and users can filter and sort locations based on different criteria.

## Description

TravelTip is an app that keeps a list of favorite locations

## Main Features

- The app allows the user to keep and manage locations
- The user can also search for an address and pan the map to that point
- The User can pan the map to his own geo-location

## Locations CRUDL

- Create – click on the map prompts for name and rate
- Read – Selected location details (see below)
- Update – can update location rate
- Delete – can delete a location
- List - Including filtering, sorting and grouping

## Selected Location

- Displayed in the header
- Location is active in the list (gold color)
- Marker on the map
- Reflected in query params
- Copy url to clipboard
- Share via Web-Share API

## Location

Here is the format of the location object:

```js
{
    id: 'GEouN',
    name: 'Dahab, Egypt',
    rate: 5,
    geo: {
      address: 'Dahab, South Sinai, Egypt',
      lat: 28.5096676,
      lng: 34.5165187,
      zoom: 11
    },
    createdAt: 1706562160181,
    updatedAt: 1706562160181
  }
```

## Services

```js
export const locService = {
  query,
  getById,
  remove,
  save,
  setFilterBy,
  setSortBy,
  getLocCountByRateMap,
}

export const mapService = {
  initMap,
  getPosition,
  setMarker,
  panTo,
  lookupAddressGeo,
  addClickListener,
}
```

## Controller

```js
// To make things easier in this project structure
// functions that are called from DOM are defined on a global app object

window.app = {
  onRemoveLoc,
  onUpdateLoc,
  onSelectLoc,
  onPanToUserPos,
  onSearchAddress,
  onCopyLoc,
  onShareLoc,
  onSetSortBy,
  onSetFilterBy,
}
```

Here is a sample usage:

```html
<button onclick="app.onCopyLoc()">Copy location</button>
<button onclick="app.onShareLoc()">Share location</button>
```

## How To Use

1. Viewing Locations:

- Locations are displayed on the map. You can click on any location to view its details, including its name, rating, and distance from your current location.

2. Adding Locations:

- Click anywhere on the map to add a new location.
- Provide a name for the location and assign a rating (between 1 to 5).

3. Updating Locations:

- Click the “Edit” button for any location to modify its rating.

4. Deleting Locations:

- Click the “Delete” button for any location to remove it.

5. Searching for Locations:

- Enter an address in the search field to pan the map to that address.

6. Filtering and Sorting Locations:

- Filter locations by name or minimum rating.

- Sort locations by rating or last updated date.

7. Sharing Locations:

- You can copy the location link or share it directly via supported apps.

## Technologies Used

Technologies Used

Frontend:

- JavaScript (Vanilla JS, ES6+)
- HTML & CSS for layout and styling
- Map API integration for geolocation and map interactions
- Swal libary for modal dialogs

## File Structure

```
css/
  /base             # base styling and layout
  /cmps             # app comonents
  /main.css         # main entry point to css files
img/                #image assets
Js/
  /services/        # JavaScript files for services like mapService, locService, etc.
  app.controller.js # Javascript file for controlling the app infront of DOM
lib/                # Javarscript libarys imported into project
index.html          # Main HTML file for the app



```
