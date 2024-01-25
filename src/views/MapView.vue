
<template>
  <div id="MapView">
    <div id="map"></div>

    <div id="VehicleSelection" class="w-full">
      <div class="w-full h-2 border-t"></div>
      <div class="w-full text-center border-t p-1.5 text-gray-700 text-lg font-semibold">
        Distance - 50
      </div>

      <div class="scrollSection">

        <div class="bg-custom-gray">
          <div class="flex items-center px-4 py-5">
            <img src="/img/uber/ride.png" alt="">
            <div class="w-full ml-3">
              <div class="flex items-center justify-between">
                <div class="text-2xl mb-1">UberX</div>
                <div class="text-xl">$55.30</div>
              </div>
              <div class="text-gray-500">7 hours</div>
            </div>
          </div>
        </div>

        <div>
          <div class="flex items-center px-4 py-5">
            <img src="/img/uber/comfort.png" alt="">
            <div class="w-full ml-3">
              <div class="flex items-center justify-between">
                <div class="text-2xl mb-1">UberX</div>
                <div class="text-xl">$55.30</div>
              </div>
              <div class="text-gray-500">7 hours</div>
            </div>
          </div>
        </div>

        <div>
          <div class="flex items-center px-4 py-5">
            <img src="/img/uber/uberxl.png" alt="">
            <div class="w-full ml-3">
              <div class="flex items-center justify-between">
                <div class="text-2xl mb-1">UberX</div>
                <div class="text-xl">$55.30</div>
              </div>
              <div class="text-gray-500">7 hours</div>
            </div>
          </div>
        </div>


      </div>

      <div
        class="
          flex
          items-center
          justify-center
          bg-white
          py-6
          px-4
          w-full
          absolute
          bottom-0
          shadow-inner
        "
      >
        <button
          class="
            bg-black
              text-2xl
              text-white
              py-4
              px-4
              rounded-sm
              w-full
            "
        >
          Confirm Uber
        </button>
      </div>

    </div>

  </div>
</template>

<script setup>
  import { onMounted } from 'vue';

  onMounted(()=>{
    
      setTimeout(()=>{
          initMap();
        },
        50
      )}
  )

  const initMap = async () => {

    const { Map } = await google.maps.importLibrary("maps");

    const map = new Map(document.getElementById("map"), {
      center: { lat: -34.397, lng: 150.644 },
      zoom: 8,
      fullscreenControl:false,
      zoomControl: false,
      streetViewControl: false,
      mapTypeControl: false
    });

    console.log(map);
  }

</script>

<style lang="scss">
  
  #MapView {

    #map {
      width: 100%;
      height: 45vh;
      top: 0px;
      left: 0px;
    }

    .gm-style-cc {
      display: none;
    }

    .bg-custom-gray {
      background-color: rgb(237, 237, 237);
    }

    #VehicleSelection {
      .scrollSection {
        height: calc(50vh - 120px);
        position: absolute;
        overflow-y: auto;
        width: 100%;
      }
    }
  }

</style>