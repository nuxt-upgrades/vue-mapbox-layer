# vue-mapbox-layer

## get api key

https://account.mapbox.com/auth/signup/ and https://account.mapbox.com/access-tokens/

import component

`import mapBox from '@/components/mapbox-layer.vue'`

and place it

```javascript
	<map-box
		act='mapbox access token'
		style='mapbox style url'
		:start='[lat,lng]'
		:geojson=''
	></map-box>

```
