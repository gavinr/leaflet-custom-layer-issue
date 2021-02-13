<script>
  import { Map as LeafletMap, Icon, Marker } from "leaflet";
  import "leaflet/dist/leaflet.css";

  const map = (domNode) => {
    const map = new LeafletMap(domNode);
    map.setView([53.35014, -6.266155], 8);
    

    var OpenStreetMap_Mapnik = L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 19,
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    });
    map.addLayer(OpenStreetMap_Mapnik);
  };
</script>

<div use:map />

<style>
  div {
    height: 100%;
    width: 100%;
  }
</style>