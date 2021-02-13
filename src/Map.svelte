<script>
  import { Map as LeafletMap, Layer, Icon, Marker } from "leaflet";
  import "leaflet/dist/leaflet.css";

  const CustomLayer = Layer.extend({
    onAdd: function (map) {
      // console.log("CUSTOM LAYER ONADD");
      const size = map.getSize();
      console.log("size:", size);
    },
  });

  const customLayer = (key, options) => {
    return new CustomLayer(key, options);
  };

  const map = (domNode) => {
    const map = new LeafletMap(domNode);
    map.setView([53.35014, -6.266155], 8);

    var OpenStreetMap_Mapnik = L.tileLayer(
      "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      {
        maxZoom: 19,
        attribution:
          '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
      }
    );
    map.addLayer(OpenStreetMap_Mapnik);

    customLayer().addTo(map);
  };
</script>

<div use:map />

<style>
  div {
    height: 100%;
    width: 100%;
  }
</style>
