<template>
  <div>
    <i-frame :src="url" />
  </div>
</template>
<script>
import iFrame from "@/components/iFrame/index";
export default {
  name: "Druid",
  components: { iFrame },
  data() {
    return {
      //knife4j
       //url: process.env.VUE_APP_BASE_API + "/doc.html"
      // swagger
      url: process.env.VUE_APP_BASE_API + "/swagger-ui"
    };
  },
};
</script>
