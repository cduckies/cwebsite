<template>
  <section class="section section--padded section--white" id="attributes">
    <div :class="[isActive ? 'filter-is-active' : '', 'container container--large']">
      <h2 class="title title--h1">Search the Flock</h2>



      <ais-instant-search :search-client="searchClient" index-name="cryptoduckies">

        <div class="filter-search">
          <ais-search-box placeholder="Search..." />
          <ais-powered-by />
        </div>


        <div class="filter-grid">

          <div class="filter-grid__sidebar">

            <div class="filter-grid__sidebar-header">
              <div @click="isActive = !isActive" class="filter-button">Close Filter</div>
              <ais-clear-refinements />
            </div>
            <div class="filter-section">
              under construction
              <!--
              <h3 class="filter-section__title">Sort by</h3>
              <ais-sort-by
                :items="[
                  { value: 'cryptoduckies', label: 'Lowest Duckie Number' },
                  { value: 'cryptoduckies_current_price_asc', label: 'Lowest Current Price' },
                  { value: 'cryptoduckies_current_price_desc', label: 'Highest Current Price' },
                  { value: 'cryptoduckies_last_sale_price_asc', label: 'Lowest Last Sale Price' },
                  { value: 'cryptoduckies_last_sale_price_desc', label: 'Highest Last Sale Price' },
                ]"
              />
              -->
            </div>
            <div class="filter-section">
              <h3 class="filter-section__title">Attributes</h3>
              <ais-refinement-list :show-more="true" :limit="25" :sort-by="['count:desc']" :show-more-limit="1000" attribute="attributes.value" />
            </div>

<!--
            <div class="filter-section">
              <h3 class="filter-section__title">Type</h3>
              <ais-refinement-list :show-more="true" :limit="3" :sort-by="['count:desc']" :show-more-limit="1000" attribute="trait_type" />
            </div>
            <div class="filter-section">
              <h3 class="filter-section__title">Body</h3>
              <ais-refinement-list :show-more="true" :limit="3" :sort-by="['count:desc']" :show-more-limit="1000" attribute="trait_type_body" />
            </div>
            <div class="filter-section">
              <h3 class="filter-section__title">Head</h3>
              <ais-refinement-list :show-more="true" :limit="3" :sort-by="['count:desc']" :show-more-limit="1000" attribute="trait_type_head" />
            </div>
            <div class="filter-section">
              <h3 class="filter-section__title">Face</h3>
              <ais-refinement-list :show-more="true" :limit="3" :sort-by="['count:desc']" :show-more-limit="1000" attribute="trait_type_face" />
            </div>
            <div class="filter-section">
              <h3 class="filter-section__title">Eyes</h3>
              <ais-refinement-list :show-more="true" :limit="3" :sort-by="['count:desc']" :show-more-limit="1000" attribute="trait_type_eyes" />
            </div>
            <div class="filter-section">
              <h3 class="filter-section__title">Beak</h3>
              <ais-refinement-list :show-more="true" :limit="3" :sort-by="['count:desc']" attribute="trait_type_beak" />
            </div>
            <div class="filter-section">
              <h3 class="filter-section__title">Background</h3>
              <ais-refinement-list :show-more="true" :limit="3" :sort-by="['count:desc']" attribute="trait_type_background" />
            </div>
            -->
          </div>

          <div class="filter-grid__results">
            <div @click="isActive = !isActive" class="filter-button">Filter</div>
            <ais-stats />

            <ais-infinite-hits>
              <template v-slot:item="{ item }">
                <a class="card" :href="item.asset_url" target="_blank">
                  <img class="card__image" :src="item.image" />
                  <span class="card__name">{{ item.name }}</span>

                  <!-- <ul class="card__prices">
                    <li>
                      <span class="card__title">Last Sold</span>
                      <div class="card__price">{{ item.last_sale_price }}<i><img src="../assets/img/eth-icon.svg"></i></div>
                    </li>
                    <li>
                      <span class="card__title" v-if="item.current_price != 'unknown' && item.current_price_symbol != 'unknown'">Current Price</span>
                      <div class="card__price" v-if="item.current_price != 'unknown' && item.current_price_symbol != 'unknown'">{{ item.current_price }}<i><img src="../assets/img/eth-icon.svg"></i></div>
                    </li>
                  </ul> -->
                </a>
              </template>
            </ais-infinite-hits>
          </div>
        </div>

      </ais-instant-search>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
import 'instantsearch.css/themes/satellite.css';
import algoliasearch from "algoliasearch/lite";

export default {
  setup() {
    const searchClient = algoliasearch(
      "7I5BN2C7FW",
      "ef8e34eab086db1556a8c6ecf598f14f"
    )
    const isActive = ref(false)
    return { searchClient, isActive };
  },
};
</script>
