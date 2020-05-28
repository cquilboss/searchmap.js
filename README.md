# searchmap.js

Open Source real estate map search in JS and WebGL.

## License

[MIT](https://choosealicense.com/licenses/mit/)

## Changelog

[CHANGELOG.md](https://github.com/cquilboss/searchmap.js/CHANGELOG.md) 

## Contributing

Pull requests are welcome.
For major changes, please open an issue first to discuss what you would like to change.

## Dependencies

- Mapbox GL JS (Free tier, more customizable and cheaper than Google Map)
- An API endpoint to get the real estate data

## Compatibility

- IE11, Edge 12
- Firefox 4+
- Chrome 8+, Android 76
- Safari 5.1, iOS Safari 8
- Opera 12

Note: see [caniuse.com/#feat=webgl](https://caniuse.com/#feat=webgl)

## Features

- Design fully customizable
- Free to use and customize
- 3 view mode: Map, List and Mix
- Automatic selection for mobile
- Mix mode ratio and left/right configurable
- Autodetect browser language
- Already translated in >20 languages
- Handle properly Right-To-Left languages like Arabic or Hebrew
- Lazy loading of the pictures
- Display 100% of the result on the map
- Allow to sort results in list mode
- Display custom POI (point of interests)
- Display Geojson polygon
- Display Custom price / total units
- Server communication optimized for performance
- Connect multiple endpoint to serve faster content
- Works on mobile
- Display active listings, sold listings and parcels
- Group listings in the same building
- Handle local cache and local storage
- Compatible with VueJS, ReactJS, AngularJS or SvelteJS
- Update browser URL
- Allow search by polygon
- SEO compliant (need some coding)

## Demo

[Custom API](https://github.com/cquilboss/searchmap.js/demo/custom.htm)

## Installation

### Manual method

Copy-paste files in dist/ to your local server and in your HTML page before </head> add

```HTML
<script src="https://api.mapbox.com/mapbox-gl-js/v1.10.1/mapbox-gl.js"></script>
<link href="https://api.mapbox.com/mapbox-gl-js/v1.10.1/mapbox-gl.css" rel="stylesheet" />
<script src="https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-draw/v1.0.9/mapbox-gl-draw.js"></script>
<link href="https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-draw/v1.0.9/mapbox-gl-draw.css" rel="stylesheet" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/vanilla-lazyload/12.3.0/lazyload.min.js"></script>
<script src="searchmap.lang.js"></script>
<script src="searchmap.js"></script>
<link href="searchmap.css" rel="stylesheet" />
```

In your HTML page after <body> add
```HTML
<div id="searchmap" class="searchmap"></div>
<script>
new SearchMap({
  container_id: "searchmap"
});
</script>
```

### Compilation method

Install via Yarn or NPM not done yet.

## Roadmap / Ideas

Below a study about some good practice in term of UX/UI found on large real estate portal or tech brokerage.

### Markers

Markers icons for properties need to be similar in order to be separate other information that can be displayed on the map. Using icon, number or colors can help to distinguishSometimes there are multiple property at the same location needs to be clear, ex. having an indication of the size (label or icon size) and separate single results.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/funda.nl.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/funda.nl.png)

[funda.nl](https://funda.nl) with 3 different icon markers (single, 1-30, multiple)

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/zillow.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/zillow.png)

[zillow.com](https://zillow.com) different colors per type

### Animation

Sometimes map navigation can be sluggish so adding animation while loading elements help users

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/seloger-anim.gif](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/seloger-anim.gif)

[seloger.com](https://seloger.com) marker animation when zoomed

### Clustering

Display all the listings on the map to avoid the feeling that properties are missing. Then do not overload the map and create dynamic clusters that varies with zoom.
Also using a indication of the size of the cluster with a number and different size is better in term of UX.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/homesnap.com.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/homesnap.com.png)

[homesnap.com](https://homesnap.com) with a number and an according circle size

### Street Number, Train Station

In real-estate it can be nice to get the street number, train station, and every helpful infomration when zoomed in.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/street-number.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/street-number.png)

[mapbox.com](https://mapbox.com) configured to display street numbers when zoom 17+

### Parcel view 🤓

When zoomed display the parcel with the estimated price

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/redfin-parcel.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/redfin-parcel.png)

[redfin.com](https://redfin.com) parcel view

### POI 🤓

Display all the point of interest around the properties. More for an advanced usage. Can also be used to generate a Walkscore.

- Transit (train, tram, bus, metro, boat, scooter, bike, wheelchair, ..)
- Schools (elementary, middle, high, private, public, ..)
- Supermarket
- Schools w/ district

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/pararius.nl.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/pararius.nl.png)

[pararius.nl](https://pararius.nl) point of interests

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/nooklyn.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/nooklyn.png)

[nooklyn.com](https://nooklyn.com) metro lines with colors

### Overlays 🤓

Display on the map information like satellite, bird view, crime, flood insurance, elevation overlays, mobile or Internet speed, etc.. Can be count-productive in some location.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/meilleursagents-price.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/meilleursagents-price.png)

[meilleursagents.com](https://meilleursagents.com) price map

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/home61.com-flood.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/home61.com-flood.png)

[home61.com](https://www.home61.com/for-sale/real-estate/) flood insurance in colors

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/realtor.com-crime-overlay.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/realtor.com-crime-overlay.png)

[realtor.com](https://realtor.com) crime in colors

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/immobilienscout24-speed.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/immobilienscout24-speed.png)

[immobilienscout24.de](https://immobilienscout24.de) internet speed on the map

### Highlight Map & List

In Mix mode (Map + List/Photo), clicking on a property in the map should highlight the property in the list, and same in the other way. The list should also scroll to be visible.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/apartment.com.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/apartment.com.png)

[apartment.com](https://apartment.com) when click on map it scroll and highlight in the list, same in the other way

### Listing already seen

Be able to identify properties already clicked, visited or in favorite help a lot.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/openlistings.com.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/openlistings.com.png)

[openlistings.com](https://openlistings.com) put marker label in gray once clicked

### Open houses

Display the coming open houses directly on the map to convert more.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/compass-openhouse.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/compass-openhouse.png)

[compass.com](https://compass.com) open houses on the map

### Properties with an approximate location

When dealing with properties we cannot geolocate like non-exclusive properties, a nice radius or polygon can help

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/bienici.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/bienici.png)

[bienici.com](https://bienici.com) with non-exclusive properties

### New properties

Display new property but also price reduced can be helpful. 

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/xome.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/xome.png)

[xome.com](https://xome.com) displays NEW listings

### Tags

Display tags, just be careful not do a rainbow of icons, for example nobody knows what stars are meaning.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/redfin.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/redfin.png)

[redfin.com](https://redfin.com/) add tags like HOT, STAR, VIDEO, EXCLUSIVE

### List mode 🤓

Instead of large picture in mix mode, having a list mode like a spreadsheet. Sometimes also possible to export into a spreadsheet.

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/redfin-list.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/redfin-list.png)

[redfin.com](https://redfin.com) list mode

### Dark mode 🤓

All new browser are now compatible with a dark mode, map can do that too

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/darkmode.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/darkmode.png)

[mapbox.com](https://mapbox.com) custom map for dark mode

### Handle Go Back

When click on the Go Back button, it should go back to the previous map search.

### Property detail

See the property detail should open a new window (ala Airbnb). Replacing the existing page make navigation difficult because going back will take too long. It's also possible to open in the property detail page in same page in a large popup like Zillow but it can render the page very heavy.

### WebGL

Thanks to WebGL [adoption](https://caniuse.com/#feat=webgl) maps can now have a 3D effect like on Waze App. Furthermore loading is far smoother than with previous Leaflet tiles. 

![https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/home61.png](https://raw.githubusercontent.com/cquilboss/searchmap.js/master/doc/home61.png)

[home61.com](https://www.home61.com) map with 30° pinch

### Performance

Page speed is important. Try to use the minimum of javascript overhead (ideally just vanilla JS). Reduce the number of HTTP call and their size. Dedicate data storage, 100% in memory, that support Spatial queries like Polygon and Point (PostGIS). MongoDB, MySQL>5.6, MariaDB and Postgres are all good solutions. Best performances are done with PostGre+PostRest then probably MongoDB. Heavily use client cache and service workers if needed. Parallelize the search queries on different datacenter and use the fastest (ala Algolia). 

### Loading animation

Should not block the navigation like click'n drag. To avoid loading when moving we can also have not checked by default "Redo search in the area option"

### Other examples

- Ratio Map/Photo
- Photo Size, Format and compression
- Photo Carousel (or Video)
- Map Property Popup (ala Zillow)
- Map boundaries, zoom limits and speed
- Property Detail (page or large popup)
- Zoom/Recenter on client location button 🤓
- Map real-time animation like Traffic, Metro, Weather, .. 🤓
- Polygon/Draw Search with "Expand Search"/"Remove outline" button 🤓
- Polygon School district 🤓
- Save & Share Search
- Favorite / Hide / Report a Property 🤓
- Property Comparison 🤓
- UTF-8 and RTL support
- Call to Action
- Display the total properties found