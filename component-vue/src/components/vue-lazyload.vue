<template>
      <div class="box">
        111
      </div>
</template>
<script>
import axios from 'axios'
export default({
  async mounted() {
    let {data:imgs} = await axios.get(' http://localhost:7300/mock/61cea344fd627c003e49cd24/api/list')
  },

})
</script>
<style>
</style>