<template>
<div style="display: block">
  <div class="custom-content-card content-card card" >
    <div class="card-body pb-0">
    <div class="content-header h4 text-center pt-2 pb-3">Highlights</div>
      <div class="row fc-charts">
        <!--<wind-status :highlights="highlights" :p_color="p_color" :s_color="s_color"></wind-status>-->
        <visibility :highlights="highlights" :p_color="p_color" :s_color="s_color"></visibility>
        <uv-index :highlights="highlights" :p_color="p_color" :s_color="s_color"></uv-index>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import UVIndex from "./UVIndex.vue";
import Visibility from "./Visibility.vue";
import WindStatus from "./WindStatus.vue";

export default {
  props: ["highlights", 'p_color', 's_color'],
  components: {
    "uv-index": UVIndex,
    "visibility": Visibility,
    "wind-status": WindStatus,
  },
};
</script>
