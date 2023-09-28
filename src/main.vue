<template>
  <div class="panelbar-wrapper">
    <PanelBar :expand-mode="'single'" :items="items">
      <template v-slot:first>
        <div>
          <div class="teamMate">
            <img :src="imageUrl('andrew')" alt="Andrew Fuller" />
            <span class="mate-info">
              <h2>Andrew Fuller</h2>
              <p>Team Lead</p>
            </span>
          </div>
          <div class="teamMate">
            <img :src="imageUrl('nancy')" alt="Andrew Fuller" />
            <span class="mate-info">
              <h2>Nancy Leverling</h2>
              <p>Sales Associate</p>
            </span>
          </div>
          <div class="teamMate">
            <img :src="imageUrl('robert')" alt="Andrew Fuller" />
            <span class="mate-info">
              <h2>Robert King</h2>
              <p>Business System Analyst</p>
            </span>
          </div>
        </div>
      </template>
    </PanelBar>
  </div>
</template>

<script>
import { PanelBar } from "@progress/kendo-vue-layout";
import "./styles.css";

export default {
  components: {
    PanelBar,
  },
  data() {
    return {
      items: [
        {
          expanded: true,
          title: "My Teammates",
          content: "first",
        },
        {
          title: "Projects",
          items: [
            { title: "New Business Plan" },
            {
              title: "Sales Forecasts",
              items: [
                { title: "Q1 Forecast" },
                { title: "Q2 Forecast" },
                { title: "Q3 Forecast" },
                { title: "Q4 Forecast" },
              ],
            },
            { title: "Sales Reports" },
          ],
        },
      ],
    };
  },
  methods: {
    imageUrl(imageName) {
      let baseImageUrl =
        "https://demos.telerik.com/kendo-ui/content/web/panelbar/";
      return baseImageUrl + imageName + ".jpg";
    },
  },
};
</script>
