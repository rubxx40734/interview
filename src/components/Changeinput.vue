<template>
    <div class="box" v-if="change == 'select'">
     <select name="" id="" class="w-25">
        <option value="">1</option>
        <option value="">2</option>
        <option value="">3</option>
     </select>
    </div>
    <input :type="change" v-else> 變形input
</template>
<script>

export default {
  data () {
    return {
      change: ''
    }
  },
  props: ['tempchange'],
  watch: {
    tempchange () {
      this.change = this.tempchange
    }
  },
  created () {

  }
}
</script>
