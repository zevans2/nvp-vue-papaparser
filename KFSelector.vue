<template>
<div class="row">
  <h2>KeepFlo Selector</h2>
  <b-button :size="lg" :variant="primary" onclick="getDistributors()">Crick Here</b-button>
</div>
</template>

<script>
  import { getDistributors } from "../scripts/handler";

  let distributors = getDistributors();
  export default {
        name: "k-f-selector",
        distributors: distributors
    }
</script>

<style scoped>

</style>
