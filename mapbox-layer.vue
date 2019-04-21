<template>
	<div class="page-map">
		<div id="map"></div>
	</div>
</template>

<script>
export default {
	props:[
		'act',
		'start',
		'geojson',
		'style',
		'click'

	],
	data: function () {
		return {
			map: null
		}
	},
	methods: {
		markers: function (geojson) {
			L.mapbox.featureLayer(geojson).
			addTo(this.map).
			on('click', function(e) {
				alert(e.sourceTarget.options.title);
			});
		},
		setMap() {
			L.mapbox.accessToken = this.act;
			this.map = L.mapbox.map('map')
			.setView(this.start, 16)
			.addLayer(L.mapbox.styleLayer(this.style));
			this.markers(this.geojson);
		},
	},
	mounted() {
		this.setMap();
	},
}
</script>

<style scoped>
	#map {
		height: 100vh;
	}
</style>