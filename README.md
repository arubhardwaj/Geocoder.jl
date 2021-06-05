# Geocoder


Geocoder.jl is a packag for geocoding. It is a part of [JuliaMaps.jl](https://github.com/arubhardwaj/JuliaMaps.jl). The idea of this project is to create something like [ggmap](https://github.com/dkahle/ggmap) for plotting maps in Julia. 

Currently, `Geocoder.jl` it can only be used as a geocoding client for Google Maps API and Open Street Maps API. It is needed to have an API key for using this package, which can be requested from [Google Cloud Console](https://console.cloud.google.com/) (for google maps) and from [Maps Quest](https://developer.mapquest.com/) (for Open Streets Map). 

For more information on requesting an API visit:

- [Google Maps Documentation](https://developers.google.com/maps/gmp-get-started)
- [MapQuest Documentation]("https://developer.mapquest.com/documentation/geocoding-api/)



# Installation

` pkg> add Geocoder`

# Usage

```julia
using JuliaMaps 
geocode("Address", "Api Key", "method")
````

Right now, JuliaMaps.jl supports only two methods: `google` and `osm`. `google` as method supports api from google maps, and `osm` supports api from Open Streets Map.

For example:

```julia
geocode("1600 Amphitheatre Parkway, Mountain View, CA", "API Key", "method")
```

For a vector, it'd be required to use [broadcasting](https://julia.guide/broadcasting) feature. For example:


```julia
geocode.(addresses, "API Key", "method")
```

`geocode()` will call the data from Google Maps API. For printing coordinates of longitudes and latitudes, execute `geometry(geocode_output)`. Example:

```julia
geocode_output = geocode("1600 Amphitheatre Parkway, Mountain View, CA", "API Key", "method")

geometry(geocode_output)
```

It is also possible to print only longitudes and only latitudes using `longitude(geocode_output)` and `latitude(geocode_output)`


# Credits

Thanks to [@dzonimn](https://github.com/dzonimn) for help in writing and checkin the functions.