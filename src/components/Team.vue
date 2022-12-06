<template>
  <section class="section overal-stats" id="team">

    <div class="container container--large">
      <h2 class="title title--h1">Team</h2>
    </div>

    <div class="container container--body ">

      <div class="rte">
        <p>Crypto Duckies are run by the community!</p>
      </div>

      <div class="team" id="team_list">

        <!--
        <div class="team__item">
          <img src="[image here]">
          <div>[name]</div>
          <span>[role]</span>
        </div> -->

      </div>
    </div>

  </section>
</template>

<script>
import { ref, computed } from "vue";
import axios from "axios";



export default {
  setup() {
    const eth_price = ref();
    const floor_price = ref("loading...");
    const total_owners = ref("loading...");
    const one_day_volume = ref("loading...");
    const one_day_change = ref("loading...");
    const total_sales = ref("loading...");
    const total_volume = ref("loading...");


    axios
      .get("https://api.opensea.io/api/v1/collections", {
        params: {
          asset_owner: "0xa4a236d97a2afa4b37693e5df8aa5afc68c42cd1",
          offset: 0,
          limit: 1,
        },
      })
      .then(function (response) {
        floor_price.value = response.data[0].stats.floor_price;
        total_owners.value = response.data[0].stats.num_owners;
        one_day_volume.value =
          Math.round(response.data[0].stats.one_day_volume * 10) / 10;
        one_day_change.value = Math.round(
          response.data[0].stats.one_day_change * 100
        );
        total_sales.value = response.data[0].stats.total_sales;
        total_volume.value = Math.round(response.data[0].stats.total_volume);
      })
      .catch(function (error) {
        console.log(error);
      });

    axios
      .get("https://api.coinbase.com/v2/prices/ETH-USD/buy")
      .then(function (response) {
        eth_price.value = Number(response.data.data.amount);
      })
      .catch(function (error) {
        console.log(error);
      });

    const floor_price_usd = computed(() => {
      return Math.round(eth_price.value * floor_price.value);
    });

    const total_owners_percentage = computed(() => {
      return Math.round((total_owners.value / 5000) * 100) + " %";
    });

    const total_volume_usd = computed(() => {
      return Math.round(eth_price.value * total_volume.value);
    });

    return {
      floor_price,
      floor_price_usd,
      total_owners,
      total_owners_percentage,
      one_day_volume,
      one_day_change,
      total_sales,
      total_volume,
      total_volume_usd,
    };
  },
};
</script>
